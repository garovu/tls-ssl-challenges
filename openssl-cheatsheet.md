# OpenSSL cheatsheet

## Generate a private key and a self-signed certificate

```shell
openssl req -x509 -nodes -newkey rsa:2048 -keyout private.key -out certificate.crt -days 365
```

## Generate a certificate signing request (CSR)

```shell
openssl req -new -newkey rsa:2048 -nodes -keyout private.key -out csr.csr
```

## Generate a certificate signing request (CSR) with a specific subject

```shell
openssl req -new -newkey rsa:2048 -nodes -keyout private.key -out csr.csr -subj "/C=US/ST=California/L=San Francisco/O=Example Company/CN=example.com"
```

## View the contents of a certificate

```shell
openssl x509 -in certificate.crt -text -noout
```

## Verify a certificate against a CA certificate

```shell
openssl verify -CAfile ca.crt certificate.crt
```

## Encrypt a file using symmetric encryption

```shell
openssl enc -aes-256-cbc -salt -in plaintext.txt -out encrypted.txt
```

## Decrypt a file using symmetric encryption

```shell
openssl enc -aes-256-cbc -d -in encrypted.txt -out decrypted.txt
```

## Generate a hash (digest) of a file

```shell
openssl dgst -sha256 file.txt
```

## Generate a random password

```shell
openssl rand -base64 16
```
