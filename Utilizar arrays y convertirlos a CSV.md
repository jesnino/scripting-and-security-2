# Utilizar arrays y convertirlos a CSV
## PowerShell 
### URL: https://www.jesusninoc.com/2017/03/14/utilizar-arrays-y-convertirlos-a-csv/
```PowerShell
$csv = @'  
Libro,Cantidad
SOM,15
ISO,16
'@ 
 
$data = $csv | ConvertFrom-Csv

$data.Libro
$data.Cantidad

$data | Out-GridView

```
