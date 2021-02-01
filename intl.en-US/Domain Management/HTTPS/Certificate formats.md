---
keyword: [certificate format, HTTPS secure acceleration, PEM format]
---

# Certificate formats

To access resources based on HTTPS secure acceleration, you must configure a Secure Sockets Layer \(SSL\) certificate. To configure an SSL certificate, you must upload the certificate content and private key in Privacy-Enhanced Mail \(PEM\) format. Different certificate authorities \(CAs\) may have different requirements on the certificate content. This topic describes the certificate formats that are supported by Alibaba Cloud Content Delivery Network \(CDN\) and how to convert different formats of certificates into the PEM format.

## Certificates issued by a root CA

Root CA certificates are issued by root CAs, including Apache, IIS, NGINX, and Tomcat. Each root CA certificate is unique. SSL certificates used by Alibaba Cloud CDN are issued by NGINX. These certificates include the `.crt` and `.key` files. Open the NGINX folder and use a text editor to open the `.crt` and `.key` files. Then, you can view the certificate content and private key that are in PEM format, as shown in the following figure.

![Certificate in PEM format](../images/p214015.png "Certificate in PEM format")

**Certificate in PEM format**

-   The certificate must start with "-----BEGIN CERTIFICATE-----" and end with "-----END CERTIFICATE-----".
-   Each line \(except the last line\) must contain 64 characters. The last line can contain 64 or fewer characters.

**Requirements on uploading certificates**

-   You must upload all content of the certificate that starts with "-----BEGIN CERTIFICATE-----" and ends with "-----END CERTIFICATE-----".
-   Each line \(except the last line\) must contain 64 characters. The last line can contain 64 or fewer characters.

## Intermediate CA certificates

A certificate file that is issued by an intermediate CA contains multiple certificates. When you configure HTTPS, you must combine the intermediate certificates and server certificate into a complete certificate before you upload it. The following figure shows an example of a complete certificate.

![A complete certificate in PEM format](../images/p214007.png "A complete certificate in PEM format")

**Format of certificate chain**

The certificates that are issued by an intermediate CA are in the following format:

-----BEGIN CERTIFICATE-----

-----END CERTIFICATE-----

-----BEGIN CERTIFICATE-----

-----END CERTIFICATE-----

-----BEGIN CERTIFICATE-----

-----END CERTIFICATE-----

**Combination rules**

Use a text editor to open all \*.PEM certificate files. When you combine the certificates, the first certificate must be the server certificate and the intermediate certificates follow the server certificate. Do not add space characters between certificates. The CA that issues the certificates may also release instructions. Pay attention to the instructions.

## Rivest–Shamir–Adleman \(RSA\) private key formats

The extension of a private key file is `.pem` or `.key`. Use a text editor to open the private key file. The following figure shows an example of a private key file.

![RSA private key formats](../images/p214176.png "RSA private key formats")

**Private key in PEM format**

-   The private key must start with "-----BEGIN RSA PRIVATE KEY-----" and end with "-----END RSA PRIVATE KEY-----".
-   Each line \(except the last line\) must contain 64 characters. The last line can contain 64 or fewer characters.

**Requirements on uploading private key**

Before you upload a RSA private key, run the `openssl genrsa -out privateKey.pem 2048` command on your on-premises machine to generate a private key. The `privateKey.pem` file is the private key file.

-   The private key must start with "-----BEGIN RSA PRIVATE KEY-----" and end with "-----END RSA PRIVATE KEY-----".
-   Each line \(except the last line\) must contain 64 characters. The last line can contain 64 or fewer characters.

If you want to generate a private key that starts with "-----BEGIN PRIVATE KEY-----" and ends with "-----END PRIVATE KEY-----", run the following command in OpenSSL to covert the format. Then, upload the content of `new_server_key.pem` and the certificate.

```
openssl rsa -in old_server_key.pem -out new_server_key.pem
```

## Convert certificate formats

The HTTPS feature supports only certificates that are in PEM format. If your certificates are not in PEM format, you must convert them into the PEM format. We recommend that you use OpenSSL to convert certificate formats. This section describes how to convert certificates into the PEM format.

**Note:**

-   The CRT file extension is short for certificate. The certificate may be in PEM or Distinguished Encoding Rules \(DER\) format. Before you convert the format of a certificate, check whether the certificate needs to be converted into other formats.
-   The PEM format is a text format. It starts with " -----BEGIN \*\*\*-----" and ends with "-----END \*\*\*-----". The content between these lines is encoded in Base64. Both the certificate and private key can be saved in this format. To distinguish a certificate from a private key, the extension of a private key file that is in PEM format is `.key`.

-   Convert a certificate from DER to PEM

    The DER format is typically used for Java.

    -   Convert the certificate format:

        ```
        openssl x509 -inform der -in certificate.cer -out certificate.pem
        ```

    -   Convert the private key format:

        ```
        openssl rsa -inform DER -outform pem -in privatekey.der -out privatekey.pem
        ```

-   Convert a certificate from P7B into PEM

    The P7B format is typically used for Windows Server and Tomcat.

    -   Convert the certificate format:

        ```
        openssl pkcs7 -print_certs -in incertificat.p7b -out outcertificate.cer
        ```

        Open the `outcertificat.cer` file. Then, copy and upload the part that starts with "-----BEGIN CERTIFICATE-----" and ends with "-----END CERTIFICATE-----".

    -   Convert the private key format:

        A certificate in P7B format does not include a private key. When you configure an SSL certificate in the Alibaba Cloud CDN console, specify the certificate information. You do not need to specify the private key information.

-   Convert a certificate from PFX into PEM

    The PFX format is typically used for Windows Server.

    -   Convert the certificate format:

        ```
        openssl pkcs12 -in certname.pfx -nokeys -out cert.pem
        ```

    -   Convert the private key format:

        ```
        openssl pkcs12 -in certname.pfx -nocerts -out key.pem -nodes
        ```


