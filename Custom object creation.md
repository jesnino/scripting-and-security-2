# Custom object creation
## PowerShell 
### URL: https://www.jesusninoc.com/2016/11/26/custom-object-creation/
```PowerShell
$propiedades = @{ 'Propiedad1' = 'Valor1'; 'Propiedad2' = 4 }
$objeto = New-Object –TypeName PSObject –Property $propiedades
$objeto | Get-Member

$objeto.Propiedad1
$objeto.Propiedad2

```
