# Listar el nombre los meses del año en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/09/09/listar-el-nombre-los-meses-del-ano-en-powershell/
```PowerShell
#Opción 1
(New-Object System.Globalization.DateTimeFormatInfo).MonthNames

#Opción 2
1..12 | % {(Get-Date).AddMonths($_).ToString("MMMM")}

```
