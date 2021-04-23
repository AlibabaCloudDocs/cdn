# Time functions

This topic describes the syntax, description, parameters, and return values of time functions. This topic also provides examples of these functions.

## today

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`today()`|
|Description|Queries the current date in the format of yyyy-mm-dd.|
|Parameter|None.|
|Return value|Returns the current date in a string in the format of yyyy-mm-dd.|
|Example|```
say(concat('today:', today()))
```

Output:```
today:2019-05-23
``` |

## time

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`time()`|
|Description|Queries the current UNIX timestamp, excluding the fractional part of milliseconds. Unit: seconds.|
|Parameter|None.|
|Return value|Returns the current UNIX timestamp.|
|Example|```
say(concat('time:', time()))
```

Output:```
time:1559109666
``` |

## now

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`now()`|
|Description|Queries the current UNIX timestamp, including the fractional part of milliseconds. Unit: seconds.|
|Parameter|None.|
|Return value|Returns the current UNIX timestamp.|
|Example|```
say(concat('now:', now()))
```

Output:```
now:1559109666.644
``` |

## localtime

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`localtime()`|
|Description|Queries the current date and time in the format of yyyy-mm-dd hh:mm:ss.|
|Parameter|None.|
|Return value|Returns the current UTC time in a string in the format of yyyy-mm-dd hh:mm:ss.|
|Example|```
say(concat('localtime:', localtime()))
```

Output:```
localtime:2019-05-29 14:02:41
``` |

## utctime

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`utctime()`|
|Description|Queries the current UTC time in the format of yyyy-mm-dd hh:mm:ss.|
|Parameter|None.|
|Return value|Returns the current UTC time in a string in the format of yyyy-mm-dd hh:mm:ss.|
|Example|```
say(concat('utctime:', utctime()))
```

Output:```
utctime:2019-05-29 06:02:41
``` |

## cookie\_time

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`cookie_time(sec)`|
|Description|Generates a time string that can be used in cookies based on a UNIX timestamp.|
|Parameter|sec: the UNIX timestamp. To query the UNIX timestamp, you can call the `time()` function.|
|Return value|Returns a time string that can be used in cookies based on the UNIX timestamp specified by the `sec` parameter.|
|Example|```
say(concat('cookie_time:', cookie_time(time())))
```

Output:```
cookie_time:Wed, 29-May-19 06:02:41 GMT
``` |

## http\_time

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`http_time(sec)`|
|Description|Generates a time string that can be used in HTTP headers based on a UNIX timestamp. For example, you can call this function to generate a time string that can be used in the Last-Modified header.|
|Parameter|sec: the UNIX timestamp. To query the UNIX timestamp, you can call the `time()` function.|
|Return value|Returns a time string that can be used in HTTP headers based on the UNIX timestamp specified by the `sec` parameter.|
|Example|```
say(concat('http_time:', http_time(time())))
```

Output```
http_time:Wed, 29 May 2019 06:02:41 GMT
``` |

## parse\_http\_time

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`parse_http_time(str)`|
|Description|Parses a time string that is used in HTTP headers and returns the corresponding UNIX timestamp.|
|Parameter|str: the time string that you want to parse. Example: `Thu, 22-Dec-10 10:20:35 GMT`. To query the time string, you can call the `http_time()` function.|
|Return value|If the function succeeds, a UNIX timestamp is returned. Otherwise, `false` is returned.|
|Example|```
say(concat('parse_http_time:', parse_http_time(http_time(time()))))
```

Output```
parse_http_time:1559109761
``` |

## UNIXtime

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`UNIXtime(year, month, day, hour, min, sec)`|
|Description|Generates and returns a UNIX timestamp based on the provided values of the year, month, day, hour, min, and sec parameters.|
|Parameter|-   year: specifies the year.
-   month: specifies the month.
-   day: specifies the day.
-   hour: specifies the hour.
-   min: specifies the minute.
-   sec: specifies the second. |
|Return value|Returns a UNIX timestamp.|
|Example|```
t = UNIXtime(1970, 1, 1, 8, 0, 0)
say(concat('UNIXtime()=', t))
```

Output```
UNIXtime()=0
``` |

