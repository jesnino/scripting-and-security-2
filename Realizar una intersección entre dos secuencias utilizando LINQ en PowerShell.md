# Realizar una intersección entre dos secuencias utilizando LINQ en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/04/realizar-una-interseccion-entre-dos-secuencias-utilizando-linq-en-powershell/
```PowerShell
[int[]] $numerosa = @(1, 2, 3, 4)
[int[]] $numerosb = @(4, 3, 7, 8)
[Linq.Enumerable]::Intersect($numerosa, $numerosb)

```
