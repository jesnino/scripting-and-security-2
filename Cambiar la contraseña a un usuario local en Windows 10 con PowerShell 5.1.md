# Cambiar la contraseña a un usuario local en Windows 10 con PowerShell 5.1
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/11/30/cambiar-la-contrasena-a-un-usuario-local-en-windows-10-con-powershell-5-1/
```PowerShell
$pass=ConvertTo-SecureString "11234aaa@@€dsf" -asplaintext -force
New-LocalUser usuario -Password $pass

Get-LocalUser

$pass2=ConvertTo-SecureString "11234aaaf" -asplaintext -force
Set-LocalUser -Name usuario -Password $pass2

```
