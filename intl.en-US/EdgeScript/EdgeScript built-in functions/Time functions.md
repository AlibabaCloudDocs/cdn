# Time functions

This topic describes the syntax, description, parameters, and response parameters of time functions. This topic also provides examples of these functions.

## today

Details about this function:

-   Syntax: `today()`.
-   Description

    Queries the current date in the format of yyyy-mm-dd.

-   Parameters

    None.

-   Response parameters

    Returns the current date in the format of yyyy-mm-dd.

-   Examples

    ```
    say(concat('today:', today()))
    
    Output:
    today:2019-05-23
    ```


## time

Details about this function:

-   Syntax: `time()`.
-   Description

    Queries the current UNIX timestamp, excluding the fractional part of milliseconds. Unit: seconds.

-   Parameters

    None.

-   Response parameters

    Returns the current UNIX timestamp.

-   Examples

    ```
    say(concat('time:', time()))
    
    Output:
    time:1559109666
    ```


## now

Details about this function:

-   Syntax: `now()`.
-   Description

    Queries the current UNIX timestamp, including the fractional part of milliseconds. Unit: seconds.

-   Parameters

    None.

-   Response parameters

    Returns the current UNIX timestamp.

-   Examples

    ```
    say(concat('now:', now()))
    
    Output:
    now:1559109666.644
    ```


## localtime

Details about this function:

-   Syntax: `localtime()`.
-   Description

    Queries the current date and time in the format of yyyy-mm-dd hh: mm: ss.

-   Parameters

    None.

-   Response parameters

    Returns the current date and time in the format of yyyy-mm-dd hh: mm: ss.

-   Examples

    ```
    say(concat('localtime:', localtime()))
    
    Output:
    localtime:2019-05-29 14:02:41
    ```


## utctime

Details about this function:

-   Syntax: `utctime()`.
-   Description

    Queries the current UTC time in the format of yyyy-mm-dd hh:mm:ss.

-   Parameters

    None.

-   Response parameters

    Returns the current UTC time in the format of yyyy-mm-dd hh:mm:ss.

-   Examples

    ```
    say(concat('utctime:', utctime()))
    
    Output:
    utctime:2019-05-29 06:02:41
    ```


## cookie\_time

Details about this function:

-   Syntax: `cookie_time(sec)`.
-   Description

    Generates a time string in the cookie time format from a UNIX timestamp.

-   Parameters

    sec: the UNIX timestamp. To obtain the UNIX timestamp, you can call the `time()` function.

-   Response parameters

    Returns a time string in the cookie time format based on the UNIX timestamp specified by the `sec` parameter.

-   Examples

    ```
    say(concat('cookie_time:', cookie_time(time())))
    
    Output:
    cookie_time:Wed, 29-May-19 06:02:41 GMT
    ```


## http\_time

Details about this function:

-   Syntax: `http_time(sec)`.
-   Description

    Generates a time string in the HTTP header time format from a UNIX timestamp. For example, this function can generate the time displayed for the Last-Modified field in the HTTP header.

-   Parameters

    sec: the UNIX timestamp. To obtain the UNIX timestamp, you can call the `time()` function.

-   Response parameters

    Returns a time string in the HTTP header time format based on the UNIX timestamp specified by the `sec` parameter.

-   Examples

    ```
    say(concat('http_time:', http_time(time())))
    
    Output:
    http_time:Wed, 29 May 2019 06:02:41 GMT
    ```


## parse\_http\_time

Details about this function:

-   Syntax: `parse_http_time(str)`.
-   Description

    Parses a time string in the HTTP header time format and returns the corresponding UNIX timestamp.

-   Parameters

    str: the time string in the HTTP header format that you want to parse. Example: `Thu, 22-Dec-10 10:20:35 GMT`. To obtain the time string, you can call the `http_time()` function.

-   Response parameters

    If the function succeeds, a UNIX timestamp is returned. Otherwise, `false` is returned.

-   Examples

    ```
    say(concat('parse_http_time:', parse_http_time(http_time(time()))))
    
    Output:
    parse_http_time:1559109761
    ```


## unixtime

Details about this function:

-   Syntax: `unixtime(year, month, day, hour, min, sec)`.
-   Description

    Generates and returns a UNIX timestamp based on the provided values of the year, month, day, hour, min, and sec parameters.

-   Parameters
    -   year: specifies the year.
    -   month: specifies the month.
    -   day: specifies the day.
    -   hour: specifies the hour.
    -   min: specifies the minute.
    -   sec: specifies the second.
-   Response parameters

    Returns a UNIX timestamp.

-   Examples

    ```
    t = unixtime(1970, 1, 1, 8, 0, 0)
    say(concat('unixtime()=', t))
    
    Output: unixtime()=0
    ```


