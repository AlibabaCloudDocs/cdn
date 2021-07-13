# Throttling functions

This topic describes the syntax, description, parameters, and return values of throttling functions. This topic also provides examples of these functions.

## limit\_rate\_after

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`limit_rate_after(n, unit)`|
|Description|Sets the maximum amount of data transfer before the data transfer rate is throttled. If the upper limit is reached, the data transfer rate is throttled.|
|Parameter|-   n: the maximum amount of data transfer before the data transfer rate is throttled. Data type: integer. If you do not set the `unit` parameter, the unit is byte.
-   unit: the unit to measure the amount of data transfer. Data type: char. This parameter is optional. Valid values of `unit`: `K`, `M`, and `G`. These values are not case-sensitive. |
|Return value|If the function succeeds, `true` is returned. Otherwise, `false` is returned.|
|Example|```
limit_rate_after(10, 'k')                                                                                                                                                              
limit_rate(1, 'm') 
//Note: Before the amount of data transfer reaches 10 KB, the data transfer rate is not throttled. If the amount of data transfer reaches 10 KB, the data transfer rate is throttled to 1 MB/s.
``` |

## limit\_rate

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`limit_rate(n, unit)`|
|Description|Sets a value to which the data transfer rate is throttled. By default, the lowest data transfer rate is 4 KB/s. If you specify a data transfer rate that is lower than 4 KB/s, the data transfer rate is throttled to 4 KB/s.|
|Parameter|-   n: the value to which you want to throttle the data transfer rate. Data type: integer. If you do not set the `unit` parameter, the unit is byte/s.
-   unit: the unit to measure the data transfer rate. Data type: char. This parameter is optional. Valid values of `unit`: `K`, `M`, and `G`. These values are not case-sensitive. |
|Return value|If the function succeeds, `true` is returned. Otherwise, `false` is returned.|
|Example|```
limit_rate_after(10, 'k')                                                                                                                                                              
limit_rate(1, 'm') 
//Note: Before the amount of data transfer reaches 10 KB, the data transfer rate is not throttled. If the amount of data transfer reaches 10 KB, the data transfer rate is throttled to 1 MB/s.
``` |

