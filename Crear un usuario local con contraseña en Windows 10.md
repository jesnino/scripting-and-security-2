# Crear un usuario local con contraseña en Windows 10
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/05/crear-un-usuario-local-con-contrasena-en-windows-10/
```PowerShell
New-LocalUser usuario -Password (ConvertTo-SecureString "11234aaadsf" -asplaintext -force)

```
