# Trabajar con objetos en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/13/trabajar-con-objetos-en-powershell/
```PowerShell
#Crear objeto coche
$coche=New-Object Object
#Añadir propiedad color de coche
Add-Member -MemberType NoteProperty -Name Color Negro -InputObject $coche
#Añadir método temperatura del motor
$coche | Add-Member ScriptMethod TemperaturaMotor {60}

#Mostrar el color del coche
$coche.color
#Mostrar la temperatura del motor
$coche.TemperaturaMotor()

```
