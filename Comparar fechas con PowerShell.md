# Comparar fechas con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/09/comparar-fechas-con-powershell/
```PowerShell
$today = "09/04/2018"
if ((Get-Date  -Format d) -eq ($today)){"Hoy es "+$today}

```
