# Comprobaciones con dígitos
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/22/comprobaciones-con-digitos/
```PowerShell
$num = 911111111

#Tiene entre 5 y 10 dígitos
$num -match '^\d{5,10}$'

#Tiene exactamente 7 dígitos
$num -match '^\d{7}$'

```
