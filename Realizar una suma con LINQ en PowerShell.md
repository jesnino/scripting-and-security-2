# Realizar una suma con LINQ en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/07/17/realizar-una-suma-con-linq-en-powershell/
```PowerShell
#Funciona
[Linq.Enumerable]::Sum([int[]](1,2))
#No funciona, es necesario indicar el tipo de dato
[Linq.Enumerable]::Sum(1,2)

```
