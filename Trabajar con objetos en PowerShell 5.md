# Trabajar con objetos en PowerShell 5
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/14/trabajar-con-objetos-en-powershell-5/
```PowerShell
#Clase coche con propiedades
class Coche
{ 
  $Marca
  $Modelo
  $FechaCompra
  $Color
}
 
#Crear objeto coche de la clase Coche
$coche=New-Object -TypeName Coche

#Añadir propiedades del coche
$coche.Marca="Audi"
$coche.Modelo="A2"
$coche.Color="Rojo"
$coche.FechaCompra= Get-Date

#Mostrar el color del coche
$coche.Color

#Mostrar información sobre el coche
$coche

```
