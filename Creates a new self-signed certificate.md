# Creates a new self-signed certificate
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/11/06/creates-a-new-self-signed-certificate/
```PowerShell
New-SelfSignedCertificate -DnsName jesusninoc -CertStoreLocation "Cert:\CurrentUser\My" -KeyUsage KeyEncipherment,DataEncipherment, KeyAgreement -Type DocumentEncryptionCert

```
