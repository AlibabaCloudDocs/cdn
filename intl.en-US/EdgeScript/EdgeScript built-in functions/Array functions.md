# Array functions

This topic describes the syntax, description, parameters, and return values of array functions. This topic also provides examples of these functions.

## arr\_concat

This function concatenates strings in a specified table by using a specified character. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|arr\_concat\(tbl, sep\)|
|Parameter|-   tbl: the table that contains the arrays to be concatenated.
-   sep: the character that is used to concatenate strings. By default, empty strings are used. This parameter is optional. |
|Example|```
d = ['t1','t2','t3']
say(arr_concat(d, '&'))
``` |
|Return value|Returns a string that is concatenated by using the specified character. In this example, `t1&t2&t3` is returned.|

## arr\_insert

This function inserts elements into an array. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|arr\_insert\(list, value, \[pos\]\)|
|Parameter|-   list: the array into which you want to insert elements.
-   value: the element that you want to insert. Data type: any type.
-   pos: a numeric value, excluding 0. The index of the array specified by list starts from 1. The element is inserted into the position specified by pos. Elements that follow the inserted element are moved towards the end of the array for one position. If you do not set the pos parameter, the element is inserted into the end of the array. |
|Example|```
tbl_1 = []
arr_insert(tbl_1, '1')
arr_insert(tbl_1, '3')
arr_insert(tbl_1, '5')
arr_insert(tbl_1, '2')
arr_insert(tbl_1, '6', 1)
str = arr_concat(tbl_1, '')
say(concat('arr_insert:', str))
``` |
|Return value|Returns `true`. In this example, `arr_insert:61352` is returned.|

## arr\_remove

This function removes elements at the specified position from an array and returns the removed elements. If you do not set the pos parameter, the element that is at the end of the array is removed. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|arr\_remove\(list, \[pos\]\)|
|Parameter|-   list: the array from which you want to remove elements.
-   pos: a numeric value. |
|Example|```
tbl_1 = []
arr_insert(tbl_1, '1')
arr_insert(tbl_1, '3')
arr_insert(tbl_1, '5')
arr_insert(tbl_1, '2')
say(concat('arr_remove:', arr_remove(tbl_1, 2)))
``` |
|Return value|Returns the element that is removed from the specified array. In this example, `arr_remove:3` is returned.|

## arr\_sort

This function sorts elements from the beginning to the end of the index in an array in a specified order.

-   If you set the camp parameter, it must be a function that supports two elements in the specified array as its parameters. A value of true is returned if the first element is placed before the second element.
-   If you do not set the camp parameter, the elements are sorted based on ANSII codes in ascending order. However, this sorting algorithm may change the original order of two elements that have the same rank in the ANSII table.

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|arr\_sort\(list, \[comp\]\)|
|Parameter|-   list: the array whose elements you want to sort.
-   comp: the sorting algorithm, which must be a function. |
|Example|```
tbl_1 = []
arr_insert(tbl_1, '1')
arr_insert(tbl_1, '3')
arr_insert(tbl_1, '5')
arr_insert(tbl_1, '2')
say(concat('remove:', arr_remove(tbl_1, 2)))
str = arr_concat(tbl_1, '')
say(concat('insert:', str))
arr_sort(tbl_1)
str = arr_concat(tbl_1, '')
say(concat('sort:', str))
def my_comp(a, b){
  a = tonumber(a)
  b = tonumber(b)
  if gt(a, b) {
    return true
  }
  return false
}
arr_sort(tbl_1, my_comp)
str = arr_concat(tbl_1, '')
say(concat('sort_comp:', str))
``` |
|Return value|Returns `true`. In this example, the following values are returned:```
remove:3
insert:152
sort:125
sort_comp:521
``` |

## arr\_len

This function counts the number of elements in an array. The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|arr\_len\(arr\)|
|Parameter|arr: the array.|
|Example|```
d = []
set(d, 1, 'v1')
say(arr_len(d))
``` |
|Return value|Returns the number of elements in the specified array. Data type: numeric. In this example, `1` is returned.|

