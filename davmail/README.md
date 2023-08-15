# DavMail

POP/IMAP/SMTP/Caldav/Carddav/LDAP Exchange and Office 365 Gateway

## Important steps when deploying
DavMail needs a certificate in PKCS12 format to be able to handle TLS connections.
To convert certificate and key created by certbot, use these commands (source: https://felix.nlogn.org/projects/davmail/)

```bash
sudo openssl rsa -aes256 -in hostname.key -out key.encrypted -passout pass:password

sudo openssl pkcs12 -export -in hostname.crt -inkey key.encrypted -certfile hostname.crt -out davmail.p12 -passin pass:password --passout pass:password
```

Adapt paths when necessary.
The password also needs to be set in the environment variables `DAVMAIL_SSL_KEYSTOREPASS` and `DAVMAIL_SSL_KEYPASS`.
