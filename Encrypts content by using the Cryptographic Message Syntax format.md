# Encrypts content by using the Cryptographic Message Syntax format
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/11/10/encrypts-content-by-using-the-cryptographic-message-syntax-format/
```PowerShell
New-SelfSignedCertificate -DnsName jesusninoc -CertStoreLocation "Cert:\CurrentUser\My" -KeyUsage KeyEncipherment,DataEncipherment, KeyAgreement -Type DocumentEncryptionCert
"Hello" | Protect-CmsMessage -To cn=jesusninoc -OutFile secret.txt

```
