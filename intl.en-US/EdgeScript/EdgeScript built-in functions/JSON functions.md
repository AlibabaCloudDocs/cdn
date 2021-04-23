# JSON functions

This topic describes the syntax, description, parameters, and return values of JSON functions. This topic also provides examples of these functions.

## json\_enc

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`json_enc(d)`|
|Description|Encodes a dictionary object into a JSON string.|
|Parameter|d: the dictionary object that you want to encode.|
|Return value|if the function succeeds, a JSON-encoded string is returned. Otherwise, `false` is returned.|
|Example|```
var_a = []
var_b = ['v1', 'v2']
set(var_a, 'k1', 'v1')
set(var_a, 'k2', var_b)
var_c = '{"k1":"v1","k2":["v1","v2"]}'
say(concat('json_enc=', json_enc(var_a)))
say(concat('json_dec=', get(json_dec(var_c), 'k1')))

Output:
json_enc={"k1":"v1","k2":["v1","v2"]}
json_dec=v1
``` |

## json\_dec

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`json_dec(s)`|
|Description|Decodes a JSON string into a dictionary.|
|Parameter|s: the JSON string that you want to decode.|
|Return value|If the function succeeds, a dictionary is returned. Otherwise, `false` is returned.|
|Example|```
var_a = []
var_b = ['v1', 'v2']
set(var_a, 'k1', 'v1')
set(var_a, 'k2', var_b)
var_c = '{"k1":"v1","k2":["v1","v2"]}'
say(concat('json_enc=', json_enc(var_a)))
say(concat('json_dec=', get(json_dec(var_c), 'k1')))

Output:
json_enc={"k1":"v1","k2":["v1","v2"]}
json_dec=v1
``` |

