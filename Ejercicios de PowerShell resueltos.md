# Ejercicios de PowerShell resueltos
## PowerShell 
### URL: https://www.jesusninoc.com/2015/01/01/ejercicios-de-powershell-resueltos/
```PowerShell
#Calcular la media de cuatro números
$numero1=2
$numero2=4
$numero3=6
$numero4=8
$media=($numero1+$numero2+$numero3+$numero4)/4
$numero1,$numero2,$numero3,$numero4 | Measure-Object -Average | Select-Object Average

#Pedir al usuario cuatro números y calcular la media
$numero1=Read-Host "Numero 1"
$numero2=Read-Host "Numero 2"
$numero3=Read-Host "Numero 3"
$numero4=Read-Host "Numero 4"
$media=($numero1+$numero2+$numero3+$numero4)/4
$numero1,$numero2,$numero3,$numero4 | Measure-Object -Average | Select-Object Average

#Tabla de multiplicar de un número
$numero=2
$multiplicar=0
do
{
Write-Host $numero "x" $multiplicar "=" $numero*$multiplicar
$multiplicar=$multiplicar+1
}while($multiplicar -le 10)

```
