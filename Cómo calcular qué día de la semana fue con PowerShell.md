# Cómo calcular qué día de la semana fue con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2016/12/26/como-calcular-que-dia-de-la-semana-fue-con-powershell/
```PowerShell
(Get-Date).AddDays(-((get-date)-([datetime]”12/22/2016 00:00”)).Days).DayOfWeek

```
