# Certificate Format {#concept_grb_4pl_xdb .concept}

Before [Enabling the HTTPS](reseller.en-US/User Guide/Domain Names/HTTPS Acceleration/HTTPS Secure Acceleration.md#) service, you must configure certificates. You can directly select managed or purchased certificates in [SSL Certificates](https://partners-intl.aliyun.com/login-required#/yundunnext), apply for free certificates, or manually upload custom certificates. Custom upload only supports certificates in `PEM` format. You must convert certificates and private keys from other formats to the PEM format.

## Certificate format requirements {#section_xgn_tpl_xdb .section}

Certificate authorities \(CAs\) generally provide the following types of certificates. Among these, Alibaba Cloud CDN uses the Nginx format \(certificates are .crt files and private keys are .key files\):

-   If certificates are issued by a root CA, you receive only one certificate.
-   If you have obtained a certificate file consisting of multiple certificates from an intermediate CA, you must manually splice the server certificate and intermediate certificate before uploading them together.

    **Note:** Splicing rules: The server certificate must be followed by the intermediate certificate without any blank line. Generally, the CA provides the relevant description when issuing a certificate. So pay attention to the rule description.


Example

Confirm the format is correct before uploading.

Certificates issued by a root CA

In Linux environments, certificates are  in the `PEM` format:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5135/15481472293703_en-US.png)

Certificate rules:

-   Upload the `-----BEGIN CERTIFICATE-----` and  `-----END  CERTIFICATE-----` content together.
-   Each line has 64 characters, but the last line can have less then 64 characters.

Certificate links issued by intermediate CAs:

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

`-----BEGIN Certificate -----`

`-----END CERTIFICATE-----`

`-----BEGIN CERTIFICATE-----`

`-----END CERTIFICATE-----`

Certificate link rules:

-   Do not insert a blank line between certificates.
-   Each certificate must comply with the certificate rules.

## RSA private key format requirements {#section_yvf_lql_xdb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5135/15481472293704_en-US.png)

RSA private key rules:

-   Run the `openssl genrsa -out privateKey.pem 2048`  command to generate a local private key, with `privateKey.pem` being the private key file.

-   `-----BEGIN RSA PRIVATE KEY-----` and ----- `END  RSA PRIVATE KEY-----`indicate the beginning and end of the private key file, respectively. Upload the beginning and end content together.

-   Each line has 64 characters, but the last line can have less than 64 characters.


If your private key is not generated in the format -----`BEGIN PRIVATE KEY-----`, 

```
——-END PRIVATE 
      KEY----- 
```

based on the preceding rules, run the following command to convert the private key:

```
openssl rsa -in old_server_key.pem -out new_server_key.pem
```

Then, upload `new_server_key.pem` content together with the certificate.

## Certificate format conversion method {#section_cn2_rql_xdb .section}

CDN HTTPS Secure Acceleration only supports certificates in the PEM format. Certificates in other formats must be converted to the PEM format. We recommend using the OpenSSL tool for conversion. The following shows the methods used to convert other common certificate  formats to PEM.

DER to PEM

The DER format is generally used on Java platforms.

-   Certificate conversion:

    ```
    openssl x509 -inform der -in certificate.cer -out certificate.pem
    ```

-   Private key conversion:

    ```
    openssl rsa -inform DER -outform pem -in privatekey.der -out privatekey.pem
    ```


P7B to PEM

The P7B format is generally used in Windows Server and Tomcat.

-   Certificate conversion:

    ```
    openssl pkcs7 -print_certs -in incertificat.p7b -out outcertificate.cer
    ```

    In `outcertificat.cer`, Retrieve the `-----BEGIN  CERTIFICATE-----`, -----END  CERTIFICATE----- `content and upload the content as a certificate`.

-   Private key conversion: P7B certificates do not have private keys, so you only have to enter the certificate portion, not the private key portion, in the CDN console.

PFX to PEM

The PFX format is generally used in Windows Server.

-   Certificate conversion:

    ```
    openssl pkcs12 -in certname.pfx -nokeys -out cert.pem
    ```

-   Private key conversion:

    ```
    openssl pkcs12 -in certname.pfx -nocerts -out key.pem -nodes
    ```


## Free certificates {#section_rbm_std_zdb .section}

The free certificate is an Alibaba Cloud CDN Digicert DV version SSL Free certificate, only available for the Alibaba Cloud CDN service. It cannot be managed in the SSL Certificates service of Alibaba Cloud Security. This certificate is only used to enable HTTPS Secure Acceleration in CDN, and you cannot obtain its public and private keys for other use.

-   The application process for a free certificate takes 5-10 minutes. While waiting, you can also go back and choose to upload a custom certificate or select a managed certificate.
-   You can always switch among custom, managed or free certificates no matter which one you enable at the beginning.
-   Free certificates are valid for one year and automatically renewed upon expiration.
-   When using this product, if you disable the HTTPS settings and then enable the free certificate option again, the system will use the free certificate you applied for previously, provided it has not expired. If your certificate has expired when you enable the free certificate option, the system reapplies for a free certificate.
-   During the application process, the system will check the DNS records of the corresponding domain to verify it points to a correct Alibaba Cloud CDN CNAME. If you request a certificate for a top-level domain, make sure to also point the `www.` subdomain at the Alibaba Cloud CDN domain. The certificate will be requested for both the top-level domain and the `www.` subdomain, so a missing CNAME record for one of those might cause an error to occur during the application.

## Other certificate issues {#section_ovq_jrl_xdb .section}

-   You can disable, enable, and modify certificates. After you disable a certificate, the system no longer retains the certificate information. When you re-enable the certificate, you must upload the certificate and private key again. See [HTTPS Secure Acceleration settings tutorial](reseller.en-US/User Guide/Domain Names/HTTPS Acceleration/HTTPS Secure Acceleration.md#).
-   Only SSL/TLS "handshakes" with SNI information are supported.
-   Ensure that the certificate and private key you upload match.
-   Certificate updates take effect in 10 minutes.
-   Private keys with passwords are not supported.

