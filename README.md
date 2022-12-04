# openssl_with_ACM

## Self Signed Certificate

A self-signed SSL certificate is an SSL Certificate that is issued by the person creating it rather than a trusted certificate authority. This can be good for testing environments.

## Step 1: Generate a CA private key
```bash
openssl genrsa -out ca.key 2048
```

## Step 2: Create a self-signed certificate, valid for 365 days
```bash
openssl req -x509 \
  -new -nodes  \
  -days 365 \
  -key ca.key \
  -out ca.crt \
  -subj "/CN=*.awsdevopstrainer.com"
```

## Open AWS ACM --> Import certificate
* Please copy contents of ```ca.crt``` to “Certificate body” and contents of ```ca.key``` to “Certificate private key”. 
* Please keep “Certificate chain” empty and click “Next” button

![image](https://user-images.githubusercontent.com/58024415/205475310-106d32d6-c47c-41c6-b1ba-5fa2665850a3.png)

* Certificate creation

![image](https://user-images.githubusercontent.com/58024415/205475327-b9cd28d3-8f5b-4965-9d0e-675d845082f8.png)
