# Unir dos secuencias utilizando LINQ en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/02/unir-dos-secuencias-utilizando-linq-en-powershell/
```PowerShell
[int[]] $numerosa = @(1, 2, 3, 4)
[int[]] $numerosb = @(5, 6, 7, 8)
[Linq.Enumerable]::Union($numerosa, $numerosb)

```
