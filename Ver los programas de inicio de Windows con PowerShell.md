# Ver los programas de inicio de Windows con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/29/ver-los-programas-de-inicio-de-windows-con-powershell/
```PowerShell
wmic startup list full | Select-String Command,Location

```
