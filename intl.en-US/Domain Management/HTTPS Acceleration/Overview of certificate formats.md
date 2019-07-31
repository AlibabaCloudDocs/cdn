# Overview of certificate formats {#concept_grb_4pl_xdb .concept}

This topic provides an overview of the certificates supported by Alibaba Cloud CDN and how to convert various certificates into PEM formats. To access resources through HTTPS secure acceleration, you must configure an HTTPS certificate.

## Root CA certificates {#section_xgn_tpl_xdb .section}

Root CA certificates are issued by root CAs including Apache, IIS, Nginx, and Tomcat. Each root CA certificate is unique. Alibaba Cloud CDN uses root CA certificates issued by Nginx. A .crt file contains certificate information and a .key file contains private key information.

A root CA certificate must conform to the following rules:

-   It starts from `-----BEGIN CERTIFICATE-----` and ends with `-----END CERTIFICATE-----`.
-   All lines except the last line must contain 64 characters.
-   The last line contains 1 to 64 characters.

The following figure shows an example certificate in PEM format when your system runs a Linux operating system.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5135/15645670523703_en-US.png)

## Intermediate CA certificates {#section_3sz_gnu_q8n .section}

A certificate file issued by an intermediate CA includes multiple certificates. You must copy and paste them at the end of the server certificate file.

**Note:** In most cases, the rules for combining the server certificate with the intermediate certificates are specified when the intermediate CA issues the certificates. Read the rules before you combine the certificates.

The chain of certificates issued by an intermediate CA is as follows:

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

The certificates in the chain must conform to the following rules:

-   Blank lines are not allowed between certificates.
-   Each certificate must be in the specified format.

## RSA private keys {#section_yvf_lql_xdb .section}

An RSA private key must conform to the following rules:

-   In the private key `openssl genrsa -out privateKey.pem 2048` generated on your computer, `privateKey.pem` is your private key file.
-   The private key starts with `-----BEGIN RSA PRIVATE KEY-----` and ends with `-----END RSA PRIVATE KEY-----`.
-   All lines except the last line must contain 64 characters.
-   The last line contains 1 to 64 characters.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5135/15645670523704_en-US.png)

If your private key does not comply with the preceding rules, for example, `-----BEGIN PRIVATE KEY-----` or `-----END PRIVATE KEY-----`\), you can convert it as follows:

``` {#codeblock_uo6_uzy_n69}
openssl rsa -in old_server_key.pem -out new_server_key.pem
```

Then, upload the `new_server_key.pem` private key file together with the certificate file.

## Convert certificate formats {#section_cn2_rql_xdb .section}

HTTPS only supports certificates in PEM format. If your certificates are not in PEM format, you must convert them into PEM formats. We recommend that you use OpenSSL to convert certificate formats. The following are methods for converting various certificates into PEM formats:

-   Certificates in DER format

    These certificates are typically used for Java.

    -   Convert a certificate from DER to PEM formats as follows:

        ``` {#codeblock_n9s_cl3_cel}
        openssl x509 -inform der -in certificate.cer -out certificate.pem
        ```

    -   Convert a private key from DER into PEM formats as follows:

        ``` {#codeblock_hp1_ex6_ohh}
        openssl rsa -inform DER -outform pem -in privatekey.der -out privatekey.pem
        ```

-   Certificates in P7B format

    These certificates are typically used for Windows Server and Tomcat.

    -   Convert a certificate from P7B to PEM formats as follows:

        ``` {#codeblock_9eq_e23_00z}
        openssl pkcs7 -print_certs -in incertificat.p7b -out outcertificate.cer
        ```

        You must copy the part starting from `-----BEGIN CERTIFICATE-----` to `-----END CERTIFICATE-----` in the `outcertificat.cer` certificate to the certificate file.

    -   A certificate in P7B format does not have a private key. When you configure an HTTPS certificate on the Alibaba Cloud console, you only need to enter the certificate information.
-   Certificates in PFX format

    These certificates are typically used for Windows Server.

    -   Convert a certificate from PFX to PEM formats as follows:

        ``` {#codeblock_jg8_cpi_omr}
        openssl pkcs12 -in certname.pfx -nokeys -out cert.pem
        ```

    -   Convert a private key from PFX to PEM formats as follows:

        ``` {#codeblock_nvn_80d_5hz}
        openssl pkcs12 -in certname.pfx -nocerts -out key.pem -nodes
        ```


