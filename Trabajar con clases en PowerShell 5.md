# Trabajar con clases en PowerShell 5
## PowerShell 
### URL: https://www.jesusninoc.com/2017/03/07/trabajar-con-clases-en-powershell-5/
```PowerShell
#Clase coche con propiedades y constructor
class Coche
{ 
  $Marca
  $Modelo
  $FechaCompra
  $Color

  #Constructor
  Coche($Marca,$FechaCompra,$Color,$Modelo)
  {
    $this.Color=$Color
    $this.Marca=$Marca
    $this.Modelo=$Modelo
    $this.FechaCompra=$FechaCompra
  }
}

#Crear objeto con valores
[Coche]::new('Rojo','Audi','A2',(get-date))

```
