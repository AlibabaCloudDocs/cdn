# Numeric functions

This topic describes the syntax, description, parameters, and return values of numeric functions. This topic also provides examples of these functions.

## add

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`add(n1, n2)`|
|Description|Calculates the sum of two addends.|
|Parameter|-   n1: the addend.
-   n2: the other addend. |
|Return value|Returns the sum of `n1 + n2`.|
|Example|```
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

Output:n1=30

n2=-10

n3=200

n4=0.5

n5=15 |

## sub

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`sub(n1, n2)`|
|Description|Calculates the difference between two numbers.|
|Parameter|-   n1: the \(minuend\) number to be subtracted from.
-   n2: the \(subtrahend\) number to be subtracted. |
|Return value|Returns the difference of `n1 - n2`.|
|Example|```
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

Output:n1=30

n2=-10

n3=200

n4=0.5

n5=15 |

## mul

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`mul(n1, n2)`|
|Description|Calculates the product of two numbers.|
|Parameter|-   n1: the multiplicand.
-   n2: the other multiplicand. |
|Return value|Returns the product of `n1 × n2`.|
|Example|```
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

Output:n1=30

n2=-10

n3=200

n4=0.5

n5=15 |

## div

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`div(n1, n2)`|
|Description|Calculates the quotient of two numbers.|
|Parameter|-   n1: the dividend.
-   n2: the divisor. |
|Return value|Returns the quotient of `n1/n2`.|
|Example|```
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

Output:n1=30

n2=-10

n3=200

n4=0.5

n5=15 |

## mod

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`mod(n1, n2)`|
|Description|Calculates the remainder after division of one number by another.|
|Parameter|-   n1: the dividend.
-   n2: the divisor. |
|Return value|Returns the remainder of `n1 % n2`.|
|Example|```
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

Output:n1=30

n2=-10

n3=200

n4=0.5

n5=15 |

## gt

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`gt(n1, n2)`|
|Description|Determines whether a number is greater than another one.|
|Parameter|-   n1: the number to be compared.
-   n2: the other number to be compared. |
|Return value|If `n1 > n2`, `true` is returned. Otherwise, `false` is returned.|
|Example|```
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

-   Request: /path1/path2/file?num=10 Response: num <= 10 num \>= 10
-   Request: /path1/path2/file?num=11 Response: num \> 10 num \>= 10
-   Request: /path1/path2/file?num=9 Response: num < 10 num <= 10 |

## ge

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`ge(n1, n2)`|
|Description|Determines whether a number is greater than or equal to another one.|
|Parameter|-   n1: the number to be compared.
-   n2: the other number to be compared. |
|Return value|If `n1 >= n2`, `true` is returned. Otherwise, `false` is returned.|
|Example|```
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

-   Request: /path1/path2/file?num=10 Response: num <= 10 num \>= 10
-   Request: /path1/path2/file?num=11 Response: num \> 10 num \>= 10
-   Request: /path1/path2/file?num=9 Response: num < 10 num <= 10 |

## lt

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`lt(n1, n2)`|
|Description|Determines whether a number is smaller than another one.|
|Parameter|-   n1: the number to be compared.
-   n2: the other number to be compared. |
|Return value|If `n1 < n2`, `true` is returned. Otherwise, `false` is returned.|
|Example|```
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

-   Request: /path1/path2/file?num=10 Response: num <= 10 num \>= 10
-   Request: /path1/path2/file?num=11 Response: num \> 10 num \>= 10
-   Request: /path1/path2/file?num=9 Response: num < 10 num <= 10 |

## le

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`le(n1, n2)`|
|Description|Determines whether a number is smaller than or equal to another one.|
|Parameter|-   n1: the number to be compared.
-   n2: the other number to be compared. |
|Return value|if `n1 <= n2`, `true` is returned. Otherwise, `false` is returned.|
|Example|```
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

-   Request: /path1/path2/file?num=10 Response: num <= 10 num \>= 10
-   Request: /path1/path2/file?num=11 Response: num \> 10 num \>= 10
-   Request: /path1/path2/file?num=9 Response: num < 10 num <= 10 |

## floor

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`floor(n)`|
|Description|Generates the greatest integer that is smaller than or equal to a number.|
|Parameter|n: the number to be rounded down.|
|Return value|Returns the greatest integer that is smaller than or equal to the number specified by`n`.|
|Example|```
if $arg_num {
    say(concat('ceil: ', ceil(tonumber($arg_num))))
    say(concat('floor: ', floor(tonumber($arg_num))))
}
```

Request: /path1/path2/file?num=9.3 Response: ceil: 10 floor: 9. |

## ceil

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`ceil(n)`|
|Description|Generates the smallest integer that is greater than or equal to a number.|
|Parameter|n: the number to be rounded up.|
|Return value|Returns the smallest integer that is greater than or equal to the number specified by`n`.|
|Example|```
if $arg_num {
    say(concat('ceil: ', ceil(tonumber($arg_num))))
    say(concat('floor: ', floor(tonumber($arg_num))))
}
```

Request: /path1/path2/file?num=9.3 Response: ceil: 10 floor: 9. |

