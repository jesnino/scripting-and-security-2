# Ver los usuarios que no han iniciado sesión en el Directorio Activo durante 100 días
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/07/ver-los-usuarios-que-no-han-iniciado-sesion-en-el-directorio-activo-durante-100-dias/
```PowerShell
Get-ADUser -Filter * -Properties LastLogonDate | ? {$_.lastlogondate -ne $null -and $_.lastlogondate -le ((get-date).adddays(-100))} | Format-List Name,LastLogonDate

```
