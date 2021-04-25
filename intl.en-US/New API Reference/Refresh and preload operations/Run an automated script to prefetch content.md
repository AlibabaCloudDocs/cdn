# Run an automated script to prefetch content

Alibaba Cloud Content Delivery Network \(CDN\) provides automated scripts that can be used to refresh and prefetch content such as files and directories from origin servers. This topic describes the features and usage notes of automated scripts. The following example demonstrates how to use an automated script to refresh and prefetch content. A Windows operating system is used in the example.

## Features

Automated scripts can be used to refresh or prefetch content from origin servers at a time or at separate times. Compared with manual operations, automated scripts greatly simplifies the process.

After you specify a file that contains URLs to be refreshed or prefetched, the automated script splits the file based on the number of concurrent refresh or prefetch tasks. The URLs are then refreshed or prefetched in batches. An automated script automatically detects whether a refresh or prefetch task is completed. The next refresh or prefetch task does not start before the current one ends.

We recommend that you use automated scripts in the following scenarios:

-   Refresh and prefetch operations are performed manually because no developer is available. The cost of operations and maintenance \(O&M\) is high.

-   The number of URLs to be refreshed or prefetched is large. Batch tasks will reduce efficiency.

-   Whether the refresh and prefetch tasks run as expected must be manually checked, which consumes a large amount of manpower and time.

## Usage notes

Before you run an automated script to refresh or prefetch content, make sure that the following environment is deployed on the on-premises machine:

-   The Alibaba Cloud CDN SDK for Python module library: The current version is 20180510. We recommend that you run the pip install aliyun-python-sdk-cdn command to install the library.
-   The Alibaba Cloud SDK for Python core library: The current version is 2.6.0. We recommend that you run the pip install aliyun-python-sdk-core commend to install the library.
-   Windows and Linux operating systems must use Python 2.75 or later. Python 3 or later is not supported.
-   Save the following code as a Refresh.py script:

    ```
    #! /usr/bin/env python
    #coding=utf-8
    # __author__ = 'hanli.zyb'
    
    '''Check Package'''
    
    try:
     import os, sys, getopt, time, json
     from aliyunsdkcore.client import AcsClient
     from aliyunsdkcore.acs_exception.exceptions import ClientException
     from aliyunsdkcore.acs_exception.exceptions import ServerException
     from aliyunsdkcdn.request.v20180510.RefreshObjectCachesRequest import RefreshObjectCachesRequest
     from aliyunsdkcdn.request.v20180510.PushObjectCacheRequest import PushObjectCacheRequest
     from aliyunsdkcdn.request.v20180510.DescribeRefreshTasksRequest import DescribeRefreshTasksRequest
     from aliyunsdkcdn.request.v20180510.DescribeRefreshQuotaRequest import DescribeRefreshQuotaRequest
    except:
     sys.exit("[Error] Please pip install aliyun-python-sdk-cdn and aliyun-python-sdk-core, please install now......")
    
    class Refresh(object):
    
      '''init func'''
    
      def __init__(self):
    
       self.lists = []
       self.param = {}
    
      '''
      Description: the main() function.
      resP: checks the input parameters. If the parameter type is not Boolean, an error occurred.
      '''
    
      def main(self,argv):
        if len(argv) < 1 :
          sys.exit("\nusage: " + sys.argv[0] + " -h ")
        try:
          opts,args = getopt.getopt(argv,"hi:k:n:r:t:a:o:")
        except Exception as e :
          sys.exit("\nusage: " + sys.argv[0] + " -h ")
      
        for opt,arg in opts:
          if opt == '-h':
            self.helps()
            sys.exit()
          elif opt == '-i':
            self.param['-i'] = arg
          elif opt == '-k':
            self.param['-k'] = arg
          elif opt == '-r':
            self.param['-r'] = arg
          elif opt == '-t':
            self.param['-t'] = arg
          elif opt == '-a':
            self.param['-a'] = arg 
          elif opt == '-o':
            self.param['-o'] = arg
          elif opt == '-n':
            self.param['-n'] = arg
          else:
            sys.exit("\nusage: " + sys.argv[0] + " -h ")
      
        resP = self.doCheck(self.param)
        if not isinstance(resP,bool): sys.exit(resP)
        
        try:
          client = AcsClient(self.param['-i'], self.param['-k'], 'cn-hangzhou')
        except NameError:
          sys.exit("[Error]: SDK module not detected")
    
        for g in self.doProd(self.param):
          self.lists = []
          self.doRefresh(''.join(g),self.param['-t'],client)
    
      '''
      Description: checks the input parameters.
      '''
      def doCheck(self,param):
    
        try:
          for key1 in ('-i','-k','-r','-t'):
            if not key1 in param.keys():
              return "[Error]: {0} Must be by parameter".format(key1)
    
          try:
            if not param.has_key('-n'):
              self.param['-n'] = 50
            if not (abs(int(param['-n'])) <= 100 and abs(int(param['-n'])) > 0):
              return "[Error]: 0 < -n <= 100"
            else:
              self.param['-n'] = int(param['-n'])
          except ValueError as e:
            return "[Error]: -n Must be int Type ,{0}".format(str(e))
    
          if not param['-t'] in ("push","clear"): return "[Error]: taskType Error"
          if param.has_key('-a') and param.has_key('-o'): return "[Error]: -a and -o cannot exist at same time"
    
          if param.has_key('-a'):
              if not param['-a'] in ("domestic","overseas"): 
                return "[Error]: Area value Error"
              if param['-t'] == 'clear':
                return "[Error]: -t must be push and 'clear' -o use together"
    
          if param.has_key('-o'):
              if not param['-o'] in ("File","Directory"):
                return "[Error]: ObjectType value Error"
              if param['-t'] == 'push':
                return "[Error]: -t must be clear and 'push' -a use together"
    
        except KeyError as e:
           return "[Error]: Parameter {0} error".format(str(e))
        return True
      
      '''
      Description: the generator splits the file by using the \n escape sequence to insert a new line.
      gop: the number of URLs to be read at a time.
      '''
      def doProd(self,params):
        gop = params['-n']
        mins = 1
        maxs = gop
    
        with open(params['-r'], "r") as f:
          for line in f.readlines():
            if mins ! = maxs:
             line = line.strip("\n") + "\n"
            else:
             line = line.strip("\n")
            self.lists.append(line)
            if mins >= maxs:
             yield self.lists
             mins = maxs
             maxs = gop + maxs -1
            else:
             mins += 1
          if len(self.lists) > 0: yield self.lists
           
      '''
      Description: the refresh or prefetch task.
      '''
      def doRefresh(self,lists,types,client):
        try:
          if types == 'clear':
            taskID = 'RefreshTaskId'
            request = RefreshObjectCachesRequest()
            if self.param.has_key('-o'):
              request.set_ObjectType(self.param['-o'])
          elif types == 'push':
            taskID = 'PushTaskId'
            request = PushObjectCacheRequest()
            if self.param.has_key('-a'):
              request.set_Area(self.param['-a'])
    
          taskreq = DescribeRefreshTasksRequest()
          request.set_accept_format('json')
          request.set_ObjectPath(lists)
          response = json.loads(client.do_action_with_exception(request))
          print(response)
        
          while True:
            count = 0
            taskreq.set_accept_format('json')
            taskreq.set_TaskId(int(response[taskID]))
            taskresp = json.loads(client.do_action_with_exception(taskreq))
            print("[" + response[taskID] + "]" + "is doing... ...")
            for t in taskresp['Tasks']['CDNTask']:
              if t['Status'] ! = 'Complete':
                count += 1
            if count == 0:
              break
            else:
              continue
            time.sleep(5)
        except Exception as e:
          sys.exit("[Error]" + str(e))
    
      '''
      Description: more information about configuring automated scripts.
      '''
      def helps(self):
        print("\nscript options explain: \
                \n\t -i <AccessKey>                  The AccessKey ID used to log on to Alibaba Cloud. You can view your AccessKey pair in the Alibaba Cloud Management console. \
                \n\t -k <AccessKeySecret>            The AccessKey secret used to log on to Alibaba Cloud. You can view your AccessKey secret in the Alibaba Cloud Management console. \
                \n\t -r <filename>                   The name of the file. Each line contains only one URL. Encode URLs that contain special characters. The encoded URLs must start with http or https. \
                \n\t -t <taskType>                   Specify the type of the task. Set the value to clear to create a refresh task. Set the value to push to create a prefetch task. \
                \n\t -n [int,[..100]]                Optional. The number of files to be managed at a time. The maximum number is 100. \
                \n\t -a [String,<domestic|overseas>  Optional. The regions in which the content will be prefetched. The default value is overseas. \
                \n\t    domestic                     Mainland China only. \
                \n\t    overseas                     Global (excluding mainland China). \
                \n\t -o [String,<File|Directory>]    Optional. The type of resource to be refreshed. \
                \n\t    File                         Files (default value). \
                \n\t    Directory                    Directories.")
    #TODO The entry point function.
    
    if __name__ == '__main__':
      fun = Refresh()
      fun.main(sys.argv[1:])
    ```


After Python is installed, you can run the python $scripte -h command in Windows Command Prompt. Relevant parameters include:

```
script options explain:
              -i <AccessKey>               //The AccessKey ID used to log on to Alibaba Cloud. You can view your AccessKey pair in the Alibaba Cloud Management console.
              -k <AccessKeySecret>    //The AccessKey secret used to log on to Alibaba Cloud. You can view your AccessKey secret in the Alibaba Cloud Management console.
              -r <filename>                 //The name of the file. Each line contains only one URL. Encode URLs that contain special characters. The encoded URLs must start with http or https.
              -t <taskType>                 //The type of the task. Set the value to clear to create a refresh task. Set the value to push to create a prefetch task.
              -n [nums,[..100]]             //Optional. The number of files to be managed at a time. The maximum number is 100.
              -a [String,<domestic|overseas>   //Optional. regions in which the content will be prefetched. The default value is Global.            
                   domestic                   //Mainland China Only.             
                   overseas                    //Global (Excluding Mainland China).             
              -o [String,<File|Directory>]    Optional. The type of resource to be refreshed.             
                   File                            //Refreshes files (default value).             
                   Directory                   //Refreshes directories.
```

## Sample scripts

In Windows Command Prompt, run the python Refresh.py -i yourAccessKey -k yourAccessKeySecret -r filename -t clear command. The following example shows the output:

```
python Refresh.py -i yourAccessKey -k yourAccessKeySecret -r /root/test/test.lst -t clear
{u'RefreshTaskId': u'8211135448', u'RequestId': u'093602B9-6192-4137-8CCA-0D8C85729DF6'}
[8211135448]is doing... ...
[8211135448]is doing... ...
[8211135448]is doing... ...
[8211135448]is doing... ...
[8211135448]is doing... ...
...
{u'RefreshTaskId': u'8211136701', u'RequestId': u'C1896DDD-003B-41F9-B481-93BC509ED5A3'}
[8211136701]is doing... ...
[8211136701]is doing... ...
...
```

