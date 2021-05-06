# EdgeScript syntax

This topic describes conventions of annotations, identifiers, data types, variables, operators, clauses, and functions in the EdgeScript \(ES\) syntax.

The following table describes the details about the ES syntax.

|Syntax|Rule|
|------|----|
|**Annotations**|All annotations must start with a number sign \(\#\). Example: \# This is annotation.|
|**Identifiers**|-   Identifiers are case-sensitive. An identifier can contain letters, digits, and underscores \(\_\). It must not start with a digit.
-   All names of built-in variables, custom variables, built-in functions, and custom functions must comply with the identifier conventions. |
|**Data types**|-   String

Literal constants: use a pair of apostrophes \(''\) to quote a literal constant, for example, `'hello, EdgeScript'`.

-   Number

Literal constants: decimal numbers, for example, 10, -99, or 1.1.

-   Boolean

Literal constants: true or false.

-   Dictionary

Literal constants:

    -   \[\]: empty string.
    -   `['key1', 'key2', 100]`:
        -   `1 -> 'key1'`
        -   `2 -> 'key2'`
        -   `3 -> 'key3'`
    -   `['key1' = 'value1', 'key2' = 1000]`
        -   `'key1' -> 'value1'`
        -   `'key2' -> 1000` |
|**Variables**|-   Definition

A variable is a symbolic name associated with a value that may change.

-   How to use
    -   Both built-in and custom variables are referenced by using their names.
        -   Reference a built-in variable: `host`.
        -   Reference a custom variable: `seckey`.
    -   To indicate that the variable is a built-in variable, add a dollar sign \(`$`\) before the variable name.

Reference a built-in variable: `$host`.

    -   Custom variables and built-in variables must not use the same name.

For more information about built-in variables, see [EdgeScript built-in variables](/intl.en-US/EdgeScript/EdgeScript built-in variables.md). |
|**Operators**|-   =: the assignment operator.
    -   Example: `seckey = 'ASDLFJ234dxvf34sDF'`
    -   Example: `seckeys = ['key1', 'key2']`
-   -: the minus operator.

Example: `inum = -10`

-   Built-in functions are used to process different types of data. No additional operators are provided. For more information about built-in functions, see [Logical functions](/intl.en-US/EdgeScript/EdgeScript built-in functions/Logical functions.md).
    -   The built-in functions support the following data types:
        -   String
        -   Numeric
        -   Dictionary
    -   Example
        -   `sval = concat(sval, 'trail')`
        -   `len(arrvar)` |
|**Clauses**|-   Condition clause

    ```
if condition {   
   ...
}

if condition1 {   
   if conditon2 {
        ...
   }
}

if condition {
   ...
} else {
   ...
}
    ```

-   Clause descriptions
    -   A `condition` clause contains the following elements:
        -   Literal constant
        -   Variable
        -   Function call
    -   Body
        -   The body can be empty.
        -   Multiple statements are allowed: only one statement is allowed on each line.
    -   Statement wrapping is allowed.
    -   CodingStyle

The opening brace \(\{\) must follow `if condition` on the same line. |
|**Functions**|-   Syntax

    ```
def Function name(Parameter list) {
   ...
}
    ```

-   Descriptions
    -   Parameter list
        -   The parameter list can be empty.
        -   Multiple parameters are allowed: separate parameters with commas \(,\).
    -   Body
        -   The body can be empty.
        -   Multiple statements are allowed: only one statement is allowed on each line.
        -   Return values: the return clause is supported.
    -   CodingStyle

The opening brace \(\{\) must follow `def` Function name\(Parameters list\) on the same line.

-   Function call

You must use `Function name()` to call both built-in and custom functions. |
|**Others**|You must not use quotation marks \("\) in ES.|

