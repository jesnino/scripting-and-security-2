# Añadir usuarios a un grupo local en Windows 10 con PowerShell 5.1
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/12/02/anadir-usuarios-a-un-grupo-local-en-windows-10-con-powershell-5-1/
```PowerShell
Add-LocalGroupMember -Member usuario -Group administradores

Get-LocalGroupMember administradores

```
