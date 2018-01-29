 
Here are the steps the create cutom ssl certificate :
1. Create private key
```openssl genrsa 2048 > my-private-key.pem```
2. Create certificate using the private key
```openssl req -new -x509 -nodes -sha256 -days 365 -key my-private-key.pem -outform PEM -out my-certificate.pem```

3. Upload certificate into AWS
```aws iam upload-server-certificate --server-certificate-name MyCertificate --certificate-body file://my-certificate.pem --private-key file://my-private-key.pem```
