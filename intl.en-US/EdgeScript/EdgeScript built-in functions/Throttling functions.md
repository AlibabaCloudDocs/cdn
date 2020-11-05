# Throttling functions

This topic describes the syntax, description, parameters, and response parameters of throttling functions. This topic also provides examples of these functions.

## limit\_rate\_after

Details about this function:

-   Syntax: `limit_rate_after(n, unit)`.
-   Description

    Sets the upper limit of the data transfer rate.

-   Parameters
    -   n: the upper limit. Data type: integer. If you do not specify the `unit` parameter, the unit is byte/s.
    -   unit: the unit to measure the data transfer rate. Data type: char. This parameter is optional. Valid values of `unit`: `K`, `M`, and `G`. These values are not case-sensitive.
-   Response parameters

    If the function succeeds, `true` is returned. Otherwise, `false` is returned.

-   Examples

    ```
    limit_rate_after(10, 'k')                                                                                                                                                              
    limit_rate(1, 'm') 
    //If the data transfer rate is lower than 10 Kbit/s, it is not throttled. If the data transfer rate is higher than 10 Kbit/s, it is throttled to 1 Mbit/s.
    ```


## limit\_rate

Details about this function:

-   Syntax: `limit_rate(n, unit)`.
-   Description

    Sets the value to which you want to throttle the data transfer rate. The lowest data transfer rate that you throttle to is 4 Kbit/s. If you specify a data transfer rate that is lower than 4 Kbit/s, the data transfer rate is throttled to 4 Kbit/s.

-   Parameters
    -   n: the lowest data transfer rate. Data type: integer. If you do not specify the `unit` parameter, the unit is byte/s.
    -   unit: the unit to measure the data transfer rate. Data type: char. This parameter is optional. Valid values of `unit`: `K`, `M`, and `G`. These values are not case-sensitive.
-   Response parameters

    If the function succeeds, `true` is returned. Otherwise, `false` is returned.

-   Examples

    ```
    limit_rate_after(10, 'k')                                                                                                                                                              
    limit_rate(1, 'm') 
    //If the data transfer rate is lower than 10 Kbit/s, it is not throttled. If the data transfer rate is higher than 10 Kbit/s, it is throttled to 1 Mbit/s.
    ```


