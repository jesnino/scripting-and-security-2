# Convertir fechas extrañas
## PowerShell 
### URL: https://www.jesusninoc.com/2017/11/13/convertir-fechas-extranas/
```PowerShell
[DateTime]::ParseExact('03 12 ********* 1988', 'MM dd ********* yyyy', $null)

```
