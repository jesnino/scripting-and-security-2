# Listar el nombre los días de la semana en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/09/13/listar-el-nombre-los-dias-de-la-semana-en-powershell/
```PowerShell
#Opción 1
(New-Object System.Globalization.DateTimeFormatInfo).DayNames

#Opción 2
1..7 | % {(Get-Date).AddDays($_).ToString("dddd")}

```
