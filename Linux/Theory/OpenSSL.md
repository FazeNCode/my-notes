OpenSSL
- Has implementation for various cryptographic operations and algorithms
- Open source
- Has implementation for Secure Socket Layer (SSL) Transport Layer Security (TLS). 

<h3> Versioning Scheme </h3>

- MAJOR: 
Shows a major release. Not backwards compatible
 
- MINOR: 
Shows a minor release, contains new features. It is backwards compatible.

- PATCH:
Shows bugs and security fixes. No new features are added. It is backwards compatible 

<h3> Libraries </h3>
-- LIBSSL --
Is used by OpenSSL to perform TLS related operations, LibSSL is dependent on LibCRYPTO 

-- LIBCRYPTO --
Is used by OpenSSL to perform cryptographic operations, such as encryption, signing, hashing and key agreement 


This will display the current version.
```
openssl version
```



https://www.ssl.com/how-to/create-a-pfx-p12-certificate-file-using-openssl/
openssl pkcs12 -export -out certificate.pfx -inkey privateKey.key -in certificate.crt -certfile more.crt

Beaking down the command:
1.) openssl – the command for executing OpenSSL
2.) pkcs12 – the file utility for PKCS#12 files in OpenSSL
3.) -export -out certificate.pfx – export and save the PFX file as certificate.pfx
4.) -inkey privateKey.key – use the private key file privateKey.key as the private key to combine with 5.) the certificate.
6.) -in certificate.crt – use certificate.crt as the certificate the private key will be combined with.
7.) -certfile more.crt – This is optional, this is if you have any additional certificates you would like to include in the PFX file.


The below command does a handsake, and displays the valid cert information
openssl s_client --connect emailaddress.com:25 -starttls smtp
