---
keyword: authentication
---

# URL signing examples

This topic uses a Python demo to demonstrate how type A signing, type B signing, and type C signing are implemented.

## Python version

For more information about the URL signing types, see the following topics:

-   [Authentication type A](/intl.en-US/Domain Management/Access control/Business type/Authentication type A.md)
-   [Authentication Type B](/intl.en-US/Domain Management/Access control/Business type/Authentication Type B.md)
-   [Authentication type C](/intl.en-US/Domain Management/Access control/Business type/Authentication type C.md)

Example:

**Note:** If the URL contains Chinese characters, you must perform URL encoding.

```
import re
import time
import hashlib
import datetime
def md5sum(src):
    m = hashlib.md5()
    m.update(src)
    return m.hexdigest()
# Type A signing
def a_auth(uri, key, exp):
    p = re.compile("^(http://|https://)?([ ^/?] +)(/[^?] *)?( \\?. *)?$")
    if not p:
        return None
    m = p.match(uri)
    scheme, host, path, args = m.groups()
    if not scheme: scheme = "http://"
    if not path: path = "/"
    if not args: args = ""
    rand = "0"      # "0" by default, other value is ok
    uid = "0"       # "0" by default, other value is ok
    sstring = "%s-%s-%s-%s-%s" %(path, exp, rand, uid, key)
    hashvalue = md5sum(sstring)
    auth_key = "%s-%s-%s-%s" %(exp, rand, uid, hashvalue)
    if args:
        return "%s%s%s%s&auth_key=%s" %(scheme, host, path, args, auth_key)
    else:
        return "%s%s%s%s? auth_key=%s" %(scheme, host, path, args, auth_key)
# Type B signing
def b_auth(uri, key, exp):
    p = re.compile("^(http://|https://)?([ ^/?] +)(/[^?] *)?( \\?. *)?$")
    if not p:
        return None
    m = p.match(uri)
    scheme, host, path, args = m.groups()
    if not scheme: scheme = "http://"
    if not path: path = "/"
    if not args: args = ""
    # convert unix timestamp to "YYmmDDHHMM" format
    nexp = datetime.datetime.fromtimestamp(exp).strftime('%Y%m%d%H%M')
    sstring = key + nexp + path
    hashvalue = md5sum(sstring)
    return "%s%s/%s/%s%s%s" %(scheme, host, nexp, hashvalue, path, args)
# Type C signing
def c_auth(uri, key, exp):
    p = re.compile("^(http://|https://)?([ ^/?] +)(/[^?] *)?( \\?. *)?$")
    if not p:
        return None
    m = p.match(uri)
    scheme, host, path, args = m.groups()
    if not scheme: scheme = "http://"
    if not path: path = "/"
    if not args: args = ""
    hexexp = "%x" %exp
    sstring = key + path + hexexp
    hashvalue = md5sum(sstring)
    return "%s%s/%s/%s%s%s" %(scheme, host, hashvalue, hexexp, path, args)
def main():
    uri = "http://xc.cdnpe.com/ping?foo=bar"            # original uri
    key = "<input private key>"                         # private key of authorization
    exp = int(time.time()) + 1 * 3600                   # expiration time: 1 hour after current itme
    authuri = a_auth(uri, key, exp)                     # auth type: a_auth / b_auth / c_auth
    print("URL : %s\nAUTH: %s" %(uri, authuri))
if __name__ == "__main__":
    main()
```

