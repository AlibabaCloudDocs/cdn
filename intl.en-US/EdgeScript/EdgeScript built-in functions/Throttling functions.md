# Throttling functions

This topic describes the syntax, description, parameters, and return values of throttling functions. This topic also provides examples of these functions.

## limit\_rate\_after

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`limit_rate_after(n, unit)`|
|Description|Sets the upper limit of the data transfer rate. If the upper limit is reached, the data transfer rate is throttled.|
|Parameter|-   n: the lowest data transfer rate. Data type: integer. If you do not set the `unit` parameter, the unit is byte/s.
-   unit: the unit to measure the data transfer rate. Data type: character. This parameter is optional. Valid values of `unit`: `K`, `M`, and `G`. These values are not case-sensitive. |
|Return value|If the function succeeds, `true` is returned. Otherwise, `false` is returned.|
|Example|```
limit_rate_after(10, 'k')                                                                                                                                                              
limit_rate(1, 'm') 
//Note: If the data transfer rate is lower than 10 Kbit/s, it is not throttled. If the data transfer rate is higher than 10 Kbit/s, it is throttled to 1 Mbit/s.
``` |

## limit\_rate

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`limit_rate(n, unit)`|
|Description|Sets the upper limit of the data transfer rate. By default, the lowest data transfer rate is 4 Kbit/s. If you specify a data transfer rate that is lower than 4 Kbit/s, the data transfer rate is throttled to 4 Kbit/s.|
|Parameter|-   n: the lowest data transfer rate. Data type: integer. If you do not set the `unit` parameter, the unit is byte/s.
-   unit: the unit to measure the data transfer rate. Data type: char. This parameter is optional. Valid values of `unit`: `K`, `M`, and `G`. These values are not case-sensitive. |
|Return value|If the function succeeds, `true` is returned. Otherwise, `false` is returned.|
|Example|```
limit_rate_after(10, 'k')                                                                                                                                                              
limit_rate(1, 'm') 
//Note: If the data transfer rate is lower than 10 Kbit/s, it is not throttled. If the data transfer rate is higher than 10 Kbit/s, it is throttled to 1 Mbit/s.
``` |

