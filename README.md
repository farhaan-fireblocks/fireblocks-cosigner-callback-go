# fireblocks-cosigner-callback-go

Callback handler implementation for Fireblocks Customer Co-signers using the Go programming language. 


Generate your callback handler private key using the following command:
```
openssl genrsa -out callback_private.pem 2048
```
Note: Only RSA 2048 bit keys are supported for public key Callback Handler response authentication.

Export the public key from the previously generated private key using the following command:
```
openssl rsa -in callback_private.pem -outform PEM -pubout -out callback_public.pem 
```

Source: [https://developers.fireblocks.com/reference/cosigner-callbackhandler-secure-communication-authentication](https://developers.fireblocks.com/reference/cosigner-callbackhandler-secure-communication-authentication)
