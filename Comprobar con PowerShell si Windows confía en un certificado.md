# Comprobar con PowerShell si Windows confía en un certificado
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/11/19/comprobar-con-powershell-si-windows-confia-en-un-certificado/
```PowerShell
$cert = Get-PfxCertificate -FilePath ".\cert.pfx"
$cert.Verify()

```
