# Numeric functions

This topic describes the syntax, description, parameters, and response parameters of numeric functions. This topic also provides examples of these functions.

## add

Details about this function:

-   Syntax: `add(n1, n2)`.
-   Description

    Calculates the sum of two addends.

-   Parameters
    -   n1: the addend.
    -   n2: the other addend.
-   Response parameters

    Returns the sum of `n1 + n2`.

-   Examples

    ```
    n1 = add(10, 20)
    n2 = sub(10, 20)
    n3 = mul(10, 20)
    n4 = div(10, 20)
    n5 = mod(35, 20)
    say(concat('n1=', n1))
    say(concat('n2=', n2))
    say(concat('n3=', n3))
    say(concat('n4=', n4))
    say(concat('n5=', n5))
    ```

    Output:

    n1=30

    n2=-10

    n3=200

    n4=0.5

    n5=15


## sub

Details about this function:

-   Syntax: `sub(n1, n2)`.
-   Description

    Calculates the difference between two numbers.

-   Parameters
    -   n1: the number to be compared.
    -   n2: the other number to be compared.
-   Response parameters

    Returns the difference of `n1 - n2`.

-   Examples

    ```
    n1 = add(10, 20)
    n2 = sub(10, 20)
    n3 = mul(10, 20)
    n4 = div(10, 20)
    n5 = mod(35, 20)
    say(concat('n1=', n1))
    say(concat('n2=', n2))
    say(concat('n3=', n3))
    say(concat('n4=', n4))
    say(concat('n5=', n5))
    ```

    Output:

    n1=30

    n2=-10

    n3=200

    n4=0.5

    n5=15


## mul

Details about this function:

-   Syntax: `mul(n1, n2)`.
-   Description

    Calculates the product of two numbers.

-   Parameters
    -   n1: the multiplicand.
    -   n2: the other multiplicand.
-   Response parameters

    Returns the product of `n1 × n2`.

-   Examples

    ```
    n1 = add(10, 20)
    n2 = sub(10, 20)
    n3 = mul(10, 20)
    n4 = div(10, 20)
    n5 = mod(35, 20)
    say(concat('n1=', n1))
    say(concat('n2=', n2))
    say(concat('n3=', n3))
    say(concat('n4=', n4))
    say(concat('n5=', n5))
    ```

    Output:

    n1=30

    n2=-10

    n3=200

    n4=0.5

    n5=15


## div

Details about this function:

-   Syntax: `div(n1, n2)`.
-   Description

    Calculates the quotient of two numbers.

-   Parameters
    -   n1: the dividend.
    -   n2: the divisor.
-   Response parameters

    Returns the quotient of `n1/n2`.

-   Examples

    ```
    n1 = add(10, 20)
    n2 = sub(10, 20)
    n3 = mul(10, 20)
    n4 = div(10, 20)
    n5 = mod(35, 20)
    say(concat('n1=', n1))
    say(concat('n2=', n2))
    say(concat('n3=', n3))
    say(concat('n4=', n4))
    say(concat('n5=', n5))
    ```

    Output:

    n1=30

    n2=-10

    n3=200

    n4=0.5

    n5=15


## mod

Details about this function:

-   Syntax: `mod(n1, n2)`.
-   Description

    Calculates the remainder after division of one number by another.

-   Parameters
    -   n1: the dividend.
    -   n2: the divisor.
-   Response parameters

    Returns the remainder of `n1 % n2`.

-   Examples

    ```
    n1 = add(10, 20)
    n2 = sub(10, 20)
    n3 = mul(10, 20)
    n4 = div(10, 20)
    n5 = mod(35, 20)
    say(concat('n1=', n1))
    say(concat('n2=', n2))
    say(concat('n3=', n3))
    say(concat('n4=', n4))
    say(concat('n5=', n5))
    ```

    Output:

    n1=30

    n2=-10

    n3=200

    n4=0.5

    n5=15


## gt

Details about this function:

-   Syntax: `gt(n1, n2)`.
-   Description

    Determines whether a number is greater than another one.

-   Parameters
    -   n1: the number to be compared.
    -   n2: the other number to be compared.
-   Response parameters

    If `n1 > n2`, `true` is returned. Otherwise, `false` is returned.

-   Examples

    ```
    if and($arg_num, gt(tonumber($arg_num), 10)) {
        say('num > 10')
    }                                                                                                                                                                                                      
    if and($arg_num, ge(tonumber($arg_num), 10)) {
        say('num >= 10')
    }
    if and($arg_num, lt(tonumber($arg_num), 10)) {
        say('num < 10')
    }                                                                                                                                                                                                       
    if and($arg_num, le(tonumber($arg_num), 10)) {
        say('num <= 10')
    }
    ```

    -   Request: /path1/path2/file? num=10 Response: num <= 10 num \>= 10
    -   Request: /path1/path2/file? num=11 Response: num \> 10 num \>= 10
    -   Request: /path1/path2/file? num=9 Response: num < 10 num <= 10

## ge

Details about this function:

-   Syntax: `ge(n1, n2)`.
-   Description

    Determines whether a number is greater than or equal to another one.

-   Parameters
    -   n1: the number to be compared.
    -   n2: the other number to be compared.
-   Response parameters

    If `n1 >= n2`, `true` is returned. Otherwise, `false` is returned.

-   Examples

    ```
    if and($arg_num, gt(tonumber($arg_num), 10)) {
        say('num > 10')
    }                                                                                                                                                                                                      
    if and($arg_num, ge(tonumber($arg_num), 10)) {
        say('num >= 10')
    }
    if and($arg_num, lt(tonumber($arg_num), 10)) {
        say('num < 10')
    }                                                                                                                                                                                                       
    if and($arg_num, le(tonumber($arg_num), 10)) {
        say('num <= 10')
    }
    ```

    -   Request: /path1/path2/file? num=10 Response: num <= 10 num \>= 10
    -   Request: /path1/path2/file? num=11 Response: num \> 10 num \>= 10
    -   Request: /path1/path2/file? num=9 Response: num < 10 num <= 10

## lt

Details about this function:

-   Syntax: `lt(n1, n2)`.
-   Description

    Determines whether a number is smaller than another one.

-   Parameters
    -   n1: the number to be compared.
    -   n2: the other number to be compared.
-   Response parameters

    If `n1 < n2`, `true` is returned. Otherwise, `false` is returned.

-   Examples

    ```
    if and($arg_num, gt(tonumber($arg_num), 10)) {
        say('num > 10')
    }                                                                                                                                                                                                      
    if and($arg_num, ge(tonumber($arg_num), 10)) {
        say('num >= 10')
    }
    if and($arg_num, lt(tonumber($arg_num), 10)) {
        say('num < 10')
    }                                                                                                                                                                                                       
    if and($arg_num, le(tonumber($arg_num), 10)) {
        say('num <= 10')
    }
    ```

    -   Request: /path1/path2/file? num=10 Response: num <= 10 num \>= 10
    -   Request: /path1/path2/file? num=11 Response: num \> 10 num \>= 10
    -   Request: /path1/path2/file? num=9 Response: num < 10 num <= 10

## le

Details about this function:

-   Syntax: `le(n1, n2)`.
-   Description

    Determines whether a number is smaller than or equal to another one.

-   Parameters
    -   n1: the number to be compared.
    -   n2: the other number to be compared.
-   Response parameters

    If `n1 <= n2`, `true` is returned. Otherwise, `false` is returned.

-   Examples

    ```
    if and($arg_num, gt(tonumber($arg_num), 10)) {
        say('num > 10')
    }                                                                                                                                                                                                      
    if and($arg_num, ge(tonumber($arg_num), 10)) {
        say('num >= 10')
    }
    if and($arg_num, lt(tonumber($arg_num), 10)) {
        say('num < 10')
    }                                                                                                                                                                                                       
    if and($arg_num, le(tonumber($arg_num), 10)) {
        say('num <= 10')
    }
    ```

    -   Request: /path1/path2/file? num=10 Response: num <= 10 num \>= 10
    -   Request: /path1/path2/file? num=11 Response: num \> 10 num \>= 10
    -   Request: /path1/path2/file? num=9 Response: num < 10 num <= 10

## floor

Details about this function:

-   Syntax: `floor(n)`.
-   Description

    Generates the greatest integer that is smaller than or equal to a number.

-   Parameters

    n: the number to be rounded down.

-   Response parameters

    Returns the greatest integer that is smaller than or equal to the number specified by`n`.

-   Examples

    ```
    if $arg_num {
        say(concat('ceil: ', ceil(tonumber($arg_num))))
        say(concat('floor: ', floor(tonumber($arg_num))))
    }
    ```

    Request: /path1/path2/file? num=9.3 Response: ceil: 10 floor: 9


## ceil

Details about this function:

-   Syntax: `ceil(n)`.
-   Description

    Generates the smallest integer that is greater than or equal to a number.

-   Parameters

    n: the number to be rounded up.

-   Response parameters

    Returns the smallest integer that is greater than or equal to the number specified by`n`.

-   Examples

    ```
    if $arg_num {
        say(concat('ceil: ', ceil(tonumber($arg_num))))
        say(concat('floor: ', floor(tonumber($arg_num))))
    }
    ```

    Request: /path1/path2/file? num=9.3 Response: ceil: 10 floor: 9


