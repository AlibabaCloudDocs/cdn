---
keyword: [certificate format, HTTPS secure acceleration, PEM format]
---

# Certificate formats

To access resources based on HTTPS secure acceleration, you must configure an HTTPS certificate. This topic describes the certificate formats that are supported by Alibaba Cloud Content Delivery Network \(CDN\) and how to convert different formats of certificates into the Privacy-Enhanced Mail \(PEM\) format.

## Root CA certificates

Root CA certificates are issued by root certificate authorities \(CAs\), including Apache, IIS, NGINX, and Tomcat. Each root CA certificate is unique. Alibaba Cloud CDN uses root CA certificates that are issued by NGINX. The certificate information is contained in a `.crt` file and the private key information is contained in a `.key` file.

The following rules apply to a root CA certificate:

-   A root CA certificate must start with `-----BEGIN CERTIFICATE-----` and end with `-----END CERTIFICATE-----`.
-   All the lines except the last line must be 64 characters in length and the last line cannot exceed 64 characters in length.

The following figure shows a sample certificate in the `PEM` format. The sample certificate is used when your system runs a Linux operating system.

![PEM](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3946219951/p3703.png)

## Intermediate CA certificates

A certificate file that is issued by an intermediate CA includes one server certificate and one intermediate certificate. You must manually concatenate the content of the server certificate and the intermediate certificate before you upload these certificates.

**Note:** Make sure that the content of the server certificate is followed by the content of the intermediate certificate. In most cases, the CA provides the description of the concatenation method when the CA issues the certificates. Follow the description to concatenate the content of the certificates.

The chain of certificates that are issued by an intermediate CA is in the following format:

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

The certificates in the chain must follow these rules:

-   Blank lines are not allowed between certificates.
-   Each certificate must be in the specified format.

## RSA private keys

A Rivest-Shamir-Adleman \(RSA\) private key must follow these rules:

-   The RSA private key must be generated based on the `openssl genrsa -out privateKey.pem 2048` command. `privateKey.pem` represents the private key file.
-   The private key must start with `-----BEGIN RSA PRIVATE KEY-----` and end with`-----END RSA PRIVATE KEY-----`.
-   All the lines except the last line must be 64 characters in length and the last line can be less than 64 characters in length.

![RSA](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3946219951/p3704.png)

If you do not generate the private key based on these rules and the private key does not start with `-----BEGIN PRIVATE KEY-----` or end with `-----END PRIVATE KEY-----`, run the following command to convert the private key:

```
openssl rsa -in old_server_key.pem -out new_server_key.pem
```

Then, upload the `new_server_key.pem` file and the certificates.

## Certificate format conversion

HTTPS configuration supports only certificates that are in the PEM format. If your certificates are not in the PEM format, you must convert them from other formats to the PEM format. We recommend that you use OpenSSL to convert certificate formats. The following section describes how to convert certificates from other formats to the PEM format:

-   Certificates in the DER format

    The Distinguished Encoding Rules \(DER\) format is typically used for Java.

    -   Convert a certificate from the DER format to the PEM format:

        ```
        openssl x509 -inform der -in certificate.cer -out certificate.pem
        ```

    -   Convert a private key from the DER format to the PEM format:

        ```
        openssl rsa -inform DER -outform pem -in privatekey.der -out privatekey.pem
        ```

-   Certificates in the P7B format

    The P7B format is typically used for Windows Server and Tomcat.

    -   Convert a certificate from the P7B format to the PEM format:

        ```
        openssl pkcs7 -print_certs -in incertificat.p7b -out outcertificate.cer
        ```

        You must open the `outcertificat.cer` file. Then, copy and paste the part that starts with `-----BEGIN CERTIFICATE-----` and ends with `-----END CERTIFICATE-----` as the certificate content.

    -   A certificate in the P7B format does not include a private key. When you configure an HTTPS certificate in the Alibaba Cloud CDN console, specify the certificate information. You do not need to specify the private key information.
-   Certificates in the PFX format

    The PFX format is typically used for Windows Server.

    -   Convert a certificate from the PFX format to the PEM format:

        ```
        openssl pkcs12 -in certname.pfx -nokeys -out cert.pem
        ```

    -   Convert a private key from the PFX format to the PEM format:

        ```
        openssl pkcs12 -in certname.pfx -nocerts -out key.pem -nodes
        ```


