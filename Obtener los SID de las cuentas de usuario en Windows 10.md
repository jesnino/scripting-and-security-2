# Obtener los SID de las cuentas de usuario en Windows 10
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2017/02/15/obtener-los-sid-de-las-cuentas-de-usuario-en-windows-10/
```PowerShell
Get-LocalUser | Select-Object Name,SID

```
