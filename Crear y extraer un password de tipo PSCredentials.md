# Crear y extraer un password de tipo PSCredentials
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/03/02/crear-y-extraer-un-password-de-tipo-pscredentials/
```PowerShell
#Crear credenciales PSCredentials
$UserName = "Domain\User"
$SecurePassword = ConvertTo-SecureString "pass23fas@@##as" -AsPlainText -Force
$Credentials = New-Object System.Management.Automation.PSCredential -ArgumentList $UserName, $SecurePassword

#Extraer password desde PSCredentials
$PlainPassword = $Credentials.GetNetworkCredential().Password
$PlainPassword

```
