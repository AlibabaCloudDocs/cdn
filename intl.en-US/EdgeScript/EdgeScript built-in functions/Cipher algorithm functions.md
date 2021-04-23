# Cipher algorithm functions

This topic describes the syntax, description, parameters, and return values of cipher algorithm functions. This topic also provides examples of these functions.

## aes\_new

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`aes_new(config)`|
|Description|Creates an Advanced Encryption Standard \(AES\) object, which is used for the subsequent encryption and decryption operations. To perform an encryption, call the `aes_enc()` function. To perform a decryption, call the `aes_dec()` function.|
|Parameter|The `config` parameter is of the dictionary type and includes the following arguments:-   key: the key, which is of the string type. This parameter is required.
-   salt: the salt value, which is of the string type. This parameter is optional.
-   cipher\_len: the length of the key. This parameter is required. Valid values: 128, 192, and 256.
-   cipher\_mode: the mode used for encryption or decryption. This parameter is required. Valid values: ecb, cbc, ctr, cfb, and ofb.
-   iv: the initial vector, which is of the string type. This parameter is optional. |
|Return value|If the function succeeds, an AES object \(dictionary type\) is returned. Otherwise,`false` is returned.|
|Example|```
aes_conf = []                                                                                                                                                                         
plaintext = ''                                                                                                                                                                        
if and($http_mode, eq($http_mode, 'ecb-128')) {                                                                                                                                       
    set(aes_conf, 'key', 'ab8bfd9f-a1af-4ba2-bbb0-1ee520e3d8bc')                                                                                                                      
    set(aes_conf, 'salt', '1234567890')                                                                                                                                               
    set(aes_conf, 'cipher_len', 128)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'ecb')                                                                                                                                               
    plaintext = 'hello aes ecb-128'                                                                                                                                                   
}                                                                                                                                                                                     
if and($http_mode, eq($http_mode, 'cbc-256')) {                                                                                                                                       
    set(aes_conf, 'key', '146ebcc8-392b-4b3a-a720-e7356f62')                                                                                                                          
    set(aes_conf, 'cipher_len', 256)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'cbc')                                                                                                                                               
    set(aes_conf, 'iv', '0123456789abcdef')                                                                                                                                           
    plaintext = 'hello aes cbc-256'                                                                                                                                                   
}                                                                                                                                                                                     
if and($http_mode, eq($http_mode, 'ofb-256')) {                                                                                                                                       
    set(aes_conf, 'key', '146ebcc8-392b-4b3a-a720-e7356f62')                                                                                                                          
    set(aes_conf, 'cipher_len', 256)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'ofb')                                                                                                                                               
    set(aes_conf, 'iv', tochar(0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0))                                                                                                                      
    plaintext = 'hello aes ofb-256'                                                                                                                                                   
}                                                                                                                                                                                     

aes_obj = aes_new(aes_conf)                                                                                                                                                           
if not(aes_obj) {                                                                                                                                                                     
    say(concat('aes obj failed'))                                                                                                                                                     
    exit(400)                                                                                                                                                                         
}                                                                                                                                                                                     

ciphertext = aes_enc(aes_obj, plaintext)                                                                                                                                              
plaintext_reverse = aes_dec(aes_obj, ciphertext)                                                                                                                                      

say(concat('plain: ', plaintext))                                                                                                                                                     
say(concat('cipher: ', tohex(ciphertext)))                                                                                                                                            
say(concat('plain_reverse: ', plaintext_reverse))                                                                                                                                     

if ne(plaintext, plaintext_reverse) {                                                                                                                                                 
    say('plaintext ~= plaintext_reverse')                                                                                                                                            
    exit(400)                                                                                                                                                                        
}
``` |

## aes\_enc

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`aes_enc(o, s)`|
|Description|Encrypts data by using the AES encryption algorithm.|
|Parameter|-   s: the plaintext to be encrypted.
-   o: the AES object returned by the `aes_new` function. |
|Return value|Returns the ciphertext after the text specified by the `s` parameter is encrypted.|
|Example|```
aes_conf = []                                                                                                                                                                         
plaintext = ''                                                                                                                                                                        
if and($http_mode, eq($http_mode, 'ecb-128')) {                                                                                                                                       
    set(aes_conf, 'key', 'ab8bfd9f-a1af-4ba2-bbb0-1ee520e3d8bc')                                                                                                                      
    set(aes_conf, 'salt', '1234567890')                                                                                                                                               
    set(aes_conf, 'cipher_len', 128)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'ecb')                                                                                                                                               
    plaintext = 'hello aes ecb-128'                                                                                                                                                   
}                                                                                                                                                                                     
if and($http_mode, eq($http_mode, 'cbc-256')) {                                                                                                                                       
    set(aes_conf, 'key', '146ebcc8-392b-4b3a-a720-e7356f62')                                                                                                                          
    set(aes_conf, 'cipher_len', 256)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'cbc')                                                                                                                                               
    set(aes_conf, 'iv', '0123456789abcdef')                                                                                                                                           
    plaintext = 'hello aes cbc-256'                                                                                                                                                   
}                                                                                                                                                                                     
if and($http_mode, eq($http_mode, 'ofb-256')) {                                                                                                                                       
    set(aes_conf, 'key', '146ebcc8-392b-4b3a-a720-e7356f62')                                                                                                                          
    set(aes_conf, 'cipher_len', 256)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'ofb')                                                                                                                                               
    set(aes_conf, 'iv', tochar(0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0))                                                                                                                      
    plaintext = 'hello aes ofb-256'                                                                                                                                                   
}                                                                                                                                                                                     

aes_obj = aes_new(aes_conf)                                                                                                                                                           
if not(aes_obj) {                                                                                                                                                                     
    say(concat('aes obj failed'))                                                                                                                                                     
    exit(400)                                                                                                                                                                         
}                                                                                                                                                                                     

ciphertext = aes_enc(aes_obj, plaintext)                                                                                                                                              
plaintext_reverse = aes_dec(aes_obj, ciphertext)                                                                                                                                      

say(concat('plain: ', plaintext))                                                                                                                                                     
say(concat('cipher: ', tohex(ciphertext)))                                                                                                                                            
say(concat('plain_reverse: ', plaintext_reverse))                                                                                                                                     

if ne(plaintext, plaintext_reverse) {                                                                                                                                                 
    say('plaintext ~= plaintext_reverse')                                                                                                                                            
    exit(400)                                                                                                                                                                        
}
``` |

## aes\_dec

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`aes_dec(o, s)`|
|Description|Decrypts data by using the AES encryption algorithm.|
|Parameter|-   s: the ciphertext to be decrypted.
-   o: the AES object returned by the `aes_new` function. |
|Return value|Returns the plaintext after the text specified by the `s` parameter is decrypted.|
|Example|```
aes_conf = []                                                                                                                                                                         
plaintext = ''                                                                                                                                                                        
if and($http_mode, eq($http_mode, 'ecb-128')) {                                                                                                                                       
    set(aes_conf, 'key', 'ab8bfd9f-a1af-4ba2-bbb0-1ee520e3d8bc')                                                                                                                      
    set(aes_conf, 'salt', '1234567890')                                                                                                                                               
    set(aes_conf, 'cipher_len', 128)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'ecb')                                                                                                                                               
    plaintext = 'hello aes ecb-128'                                                                                                                                                   
}                                                                                                                                                                                     
if and($http_mode, eq($http_mode, 'cbc-256')) {                                                                                                                                       
    set(aes_conf, 'key', '146ebcc8-392b-4b3a-a720-e7356f62')                                                                                                                          
    set(aes_conf, 'cipher_len', 256)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'cbc')                                                                                                                                               
    set(aes_conf, 'iv', '0123456789abcdef')                                                                                                                                           
    plaintext = 'hello aes cbc-256'                                                                                                                                                   
}                                                                                                                                                                                     
if and($http_mode, eq($http_mode, 'ofb-256')) {                                                                                                                                       
    set(aes_conf, 'key', '146ebcc8-392b-4b3a-a720-e7356f62')                                                                                                                          
    set(aes_conf, 'cipher_len', 256)                                                                                                                                                  
    set(aes_conf, 'cipher_mode', 'ofb')                                                                                                                                               
    set(aes_conf, 'iv', tochar(0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0))                                                                                                                      
    plaintext = 'hello aes ofb-256'                                                                                                                                                   
}                                                                                                                                                                                     

aes_obj = aes_new(aes_conf)                                                                                                                                                           
if not(aes_obj) {                                                                                                                                                                     
    say(concat('aes obj failed'))                                                                                                                                                     
    exit(400)                                                                                                                                                                         
}                                                                                                                                                                                     

ciphertext = aes_enc(aes_obj, plaintext)                                                                                                                                              
plaintext_reverse = aes_dec(aes_obj, ciphertext)                                                                                                                                      

say(concat('plain: ', plaintext))                                                                                                                                                     
say(concat('cipher: ', tohex(ciphertext)))                                                                                                                                            
say(concat('plain_reverse: ', plaintext_reverse))                                                                                                                                     

if ne(plaintext, plaintext_reverse) {                                                                                                                                                 
    say('plaintext ~= plaintext_reverse')                                                                                                                                            
    exit(400)                                                                                                                                                                        
}
``` |

## sha1

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`sha1(s)`|
|Description|Calculates an SHA-1 value.|
|Parameter|s: the string for which you want to calculate a CRC digest.|
|Return value|Returns an SHA-1 value in binary format.|
|Example|```
digest = sha1('hello sha')                                                                                                                                                        
say(concat('sha1:', tohex(digest)))

Output:
sha1:853789bc783a6b573858b6cc9f913afe82962956
``` |

## sha2

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`sha2(s, l)`|
|Description|Calculates an SHA-2 value.|
|Parameter|-   s: the string for which you want to calculate a CRC digest.
-   l: the length of the SHA-2 value. Valid values: 224, 256, 384, and 512. |
|Return value|Returns an SHA-2 value in binary format.|
|Example|```
digest = sha2('hello sha2', 224)
say(concat('sha2-224:', tohex(digest)))

digest = sha2('hello sha2', 256)
say(concat('sha2-256:', tohex(digest)))

digest = sha2('hello sha2', 384)
say(concat('sha2-384:', tohex(digest)))

digest = sha2('hello sha2', 512)
say(concat('sha2-512:', tohex(digest)))

Output:
sha2-224:b24b7effcf53ce815ee7eb73c7382613aba1c334e2a1622655362927
sha2-256:af0425cee23c236b326ed1f008c9c7c143a611859a11e87d66d0a4c3217c7792
sha2-384:bebbdde9efabd4b9cf90856cf30e0b024dd13177d9367d2dcf8d7a04e059f92260f16b21e261358c2271be32086ef35b
sha2-512:a1d1aef051c198c0d26bc03500c177a315fa248cea815e04fbb9a75e5be5061617daab311c5e3d0b215dbfd4e83e73f23081242b0143dcdfce5cd92ec51394f7
``` |

## hmac

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`hmac(k, s, v)`|
|Description|Calculates an HMAC value.|
|Parameter|-   k: the key of the algorithm.
-   s: the string for which you want to calculate an HMAC value.
-   v: the version of the algorithm. Valid values: md5, sha256, and sha512. |
|Return value|Returns an HMAC value in binary format by using the corresponding algorithm.|
|Example|```
k = '146ebcc8-392b-4b3a-a720-e7356f62f87b'
v = 'hello mac'
say(concat('hmac(md5): ', tohex(hmac(k, v, 'md5'))))
say(concat('hmac(sha1): ', tohex(hmac(k, v, 'sha1'))))
say(concat('hmac(sha256): ', tohex(hmac(k, v, 'sha256'))))
say(concat('hmac(sha512): ', tohex(hmac(k, v, 'sha512'))))
say(concat('hmac_sha1(): ', tohex(hmac_sha1(k, v))))

Output:
hmac(md5): 358cbfca8ad663b547c83748de2ea778
hmac(sha1): 5555633cef48c3413b68f9330e99357df1cc3d93
hmac(sha256): 7a494543cad3b92ce1e7c4bbc86a8f5212b53e4d661f7830f455847540a85771
hmac(sha512): 59d7c07996ff675b45bd5fd40a6122bb5f40f597357a9b4a9e29da6f5c7cb806798c016fe09cb46457b6df9717d26d0af19896f72eaf4296be03e3681fea59ad
hmac_sha1(): 5555633cef48c3413b68f9330e99357df1cc3d93
``` |

## hmac\_sha1

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`hmac_sha1(k, s)`|
|Description|Calculates an HMAC-SHA-1 value.|
|Parameter|-   s: the string for which you want to calculate an HMAC-SHA-1 value.
-   k: the HMAC-SHA-1 key. |
|Return value|Returns an HMAC-SHA-1 value in binary format.|
|Example|```
k = '146ebcc8-392b-4b3a-a720-e7356f62f87b'
v = 'hello mac'
say(concat('hmac(md5): ', tohex(hmac(k, v, 'md5'))))
say(concat('hmac(sha1): ', tohex(hmac(k, v, 'sha1'))))
say(concat('hmac(sha256): ', tohex(hmac(k, v, 'sha256'))))
say(concat('hmac(sha512): ', tohex(hmac(k, v, 'sha512'))))
say(concat('hmac_sha1(): ', tohex(hmac_sha1(k, v))))

Output:
hmac(md5): 358cbfca8ad663b547c83748de2ea778
hmac(sha1): 5555633cef48c3413b68f9330e99357df1cc3d93
hmac(sha256): 7a494543cad3b92ce1e7c4bbc86a8f5212b53e4d661f7830f455847540a85771
hmac(sha512): 59d7c07996ff675b45bd5fd40a6122bb5f40f597357a9b4a9e29da6f5c7cb806798c016fe09cb46457b6df9717d26d0af19896f72eaf4296be03e3681fea59ad
hmac_sha1(): 5555633cef48c3413b68f9330e99357df1cc3d93
``` |

## md5

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`md5(s)`|
|Description|Calculates an MD5 digest.|
|Parameter|s: the string for which you want to calculate a CRC digest.|
|Return value|Returns an MD5 value in hexadecimal format.|
|Example|```
say(concat('md5: ', md5('hello md5')))

Output:
md5: 741fc6b1878e208346359af502dd11c5
``` |

## md5\_bin

The following table describes the details about this function.

|Item|Description|
|----|-----------|
|Syntax|`md5_bin(s)`|
|Description|Calculates an MD5 digest.|
|Parameter|s: the string for which you want to calculate a CRC digest.|
|Return value|Returns an MD5 digest in binary format.|
|Example|```
say(concat('md5_bin: ', tohex(md5_bin('hello md5'))))

Output:
md5_bin: 741fc6b1878e208346359af502dd11c5
``` |

