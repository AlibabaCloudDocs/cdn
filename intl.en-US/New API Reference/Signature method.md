# Signature method

This topic describes how requests are signed. You must sign all HTTP or HTTPS API requests to ensure security. Alibaba Cloud uses the request signature to verify the identity of the request sender. Alibaba Cloud Content Delivery Network \(CDN\) implements symmetric encryption with an AccessKey pair to verify the identity of the request sender. An AccessKey pair consists of an AccessKey ID and an AccessKey secret.

## AccessKey descriptions

You can obtain the AccessKey ID and AccessKey secret on the AccessKey Management page in the Alibaba Cloud Management Console. The AccessKey ID is used to verify the identity of the user, while the AccessKey secret is used to encrypt and verify the signature string. You must keep your AccessKey secret strictly confidential.

For more information, see [t1831133.md\#](/intl.en-US/New API Reference/Obtain an AccessKey pair.md).

## Procedure

1.  Create a canonicalized query string.

    1.  Arrange the request parameters \(including [Common request parameters](/intl.en-US/New API Reference/Common request parameters.md) and operation-specific parameters except Signature\) in alphabetical order.

        **Note:** If you use the GET method to send a request, the request parameters are included as a part of the request URL. The first parameter follows the question mark \(`?`\) in the URL and the other parameters follow an ampersand \(`&`\).

    2.  Encode the canonicalized query string in UTF-8 based on [RFC 3986](https://tools.ietf.org/html/rfc3986?spm=a2c63.p38356.a3.6.3a162674ma72Hg).
        -   Uppercase letters, lowercase letters, digits, and some special characters such as hyphens \(`-`\), underscores \(`_`\), periods \(`.`\), and tildes \(`~`\) do not need to be encoded.
        -   Other characters must be percent encoded in `%XY` format. `XY` represents the ASCII code of the characters in hexadecimal notation.

            For example, double quotation marks \("\) are encoded as `%22`.

        -   Extended UTF-8 characters are encoded in `%XY%ZA...` format.
        -   Spaces must be encoded as `%20`. Do not encode spaces as plus signs \(+\). The preceding encoding method is slightly different from the application/x-www-form-urlencoded MIME-type encoding algorithm. If you use `java.net.URLEncoder` in the Java standard library, use `percentEncode` to encode request parameters and their values. In the encoded query string, replace the plus sign \(+\) with `%20`, the asterisk \(\*\) with `%2A`, and `%7E` with a tilde \(~\). This way, you can obtain an encoded string that matches the preceding encoding rules.
    3.  Use an equal sign \(=\) to concatenate each encoded request parameter and its value.
    4.  Use an ampersand \(&\) to concatenate the encoded request parameters. Note that these parameters must be arranged in the same order as those in [Step 1](#li_stk_6v7_yry).
2.  Create a string-to-sign.

    1.  Create a string-to-sign \(Signature\) from the encoded canonicalized query string.

        You can also use percentEncode to encode the canonicalized query string created in the previous step. Perform the following steps to create a string-to-sign:

        ```
        StringToSign=
        HTTPMethod + "&" + // HTTPMethod: HTTP method used to make the request, such as GET.
        percentEncode ("/") + "&" + //percentEncode("/"): encode backslashes (/) as %2F.
        percentEncode(CanonicalizedQueryString) // encode the canonicalized query string created in Step 1.
        ```

    2.  Calculate the HMAC value of the string-to-sign by using the AccessKey secret as the key.

        Calculate the hash-based message authentication code \(HMAC\) value of the string-to-sign based on [RFC 2104](https://www.ietf.org/rfc/rfc2104.txt?spm=5176.doc54229.2.7.2jcEcp&file=rfc2104.txt).

        **Note:** Use the Secure Hash Algorithm 1 \(SHA1\) algorithm to calculate the HMAC value of the string-to-sign. The AccessKey secret appended with an ampersand \(`&`\) \(ASCII: 38\) is used as the key for the HMAC calculation.

    3.  Obtain the signature string.

        Encode the HMAC value in [Base64](https://wenku.baidu.com/view/1b9ea72bed630b1c59eeb579.html?spm=5176.doc54229.2.8.2jcEcp) to obtain the signature string \(Signature\).

    4.  Add the signature string to the request.

        Add the signature string to the request as the Signature parameter. The result is the signed API request.

        **Note:** The signature string is submitted to the server based on [RFC 3986](http://tools.ietf.org/html/rfc3986?spm=5176.doc54229.2.9.2jcEcp).


