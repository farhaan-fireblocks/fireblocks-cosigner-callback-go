# Co-signer Callback Handler Setup (Go)

This guide explains how to implement a callback handler for Fireblocks Customer Co-signers using Go. Communication is secured via [public key authentication](https://developers.fireblocks.com/reference/cosigner-callbackhandler-secure-communication-authentication#option-1-public-key-authentication).

## Prerequisites
Before running the callback handler, please complete the following steps:

### 1) Generate a Key Pair for your callback handler.

Generate an RSA 2048-bit key pair to secure your handler's responses.

Generate Private Key: 
```
openssl genrsa -out callback_private.pem 2048
```

Export Public Key:
```
openssl rsa -in callback_private.pem -outform PEM -pubout -out callback_public.pem 
```
Reference to Fireblocks documentation: [https://developers.fireblocks.com/reference/cosigner-callbackhandler-secure-communication-authentication#jwt-encoded-signed-request](https://developers.fireblocks.com/reference/cosigner-callbackhandler-secure-communication-authentication#jwt-encoded-signed-request)

### 2) Retrieve the Co-signer Public Key

You must retrieve the public key from your Co-signer VM. Refer to the specific guide for your cloud provider:
- [AWS Nitro Enclaves]([https://developers.fireblocks.com/reference/api-cosigner-maintenance-aws-nitro](https://developers.fireblocks.com/reference/api-cosigner-maintenance-aws-nitro#retrieve-the-public-key))
- [Azure SGX](https://developers.fireblocks.com/reference/api-cosigner-maintenance-sgx#retrieve-the-public-key)
- [GCP Confidential Space](https://developers.fireblocks.com/reference/api-cosigner-maintenance-gcp-confspace#retrieve-the-public-key)

### 3) Local Testing (Optional)

For local development, you can use a tunneling service or gateway of your choice, such as:
- [Cloudflare Tunnel](https://try.cloudflare.com/)
- [ngrok](https://ngrok.com/)


At the end of the setup process, you should have the following three files: callback_private.pem, callback_public.pem, and cosigner_public.pem.


