# Codificar en Base64 paso a paso con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/01/13/codificar-en-base64-paso-a-paso-con-powershell/
```PowerShell
##########################################################################################################
#Texto en ASCII
##########################################################################################################
$val="hola"

##########################################################################################################
#Representar el texto ASCII en HEX
Write-Host "#############################################################"
Write-Host "Representar el texto ASCII en HEX"
Write-Host "#############################################################"
##########################################################################################################
0..($val.Length-1) | %{
$cadenah=[System.String]::Format("{0:X}", [System.Convert]::ToUInt32($val[$_]))
Write-Host $val[$_],$cadenah
}

##########################################################################################################
#Representar el texto ASCII en binario
Write-Host "#############################################################"
Write-Host "Representar el texto ASCII en binario"
Write-Host "#############################################################"
#Los caracteres que tienen 6 bits de representación se añaden dos bits delante para que sean 8 bits
#Los caracteres que tienen 7 bits de representación se añaden un bit delante para que sean 8 bits
##########################################################################################################
$cadenabalmacen=""
0..($val.Length-1) | %{
$cadenah=[System.String]::Format("{0:X}", [System.Convert]::ToUInt32($val[$_]))
$cadenab=([Convert]::ToString([Byte]::Parse($cadenah,[System.Globalization.NumberStyles]::HexNumber),2))

if($cadenab.Length -eq 6){$cadenab="00"+$cadenab}
if($cadenab.Length -eq 7){$cadenab="0"+$cadenab}

#Almacenar todos los valores representados en una variable
$cadenabalmacen+=$cadenab
Write-Host $cadenah,$cadenab
}
$cadenabalmacen

##########################################################################################################
#Crear grupos de 6 bits para el resultado de la representación del texto ASCII en binario
Write-Host "#############################################################"
Write-Host "Crear grupos de 6 bits para el resultado de la representación del texto ASCII en binario"
Write-Host "#############################################################"
##########################################################################################################
for($i=0;$i -lt $cadenabalmacen.Length; $i=$i+6)
{
[String]$cadenabalmacen[($i)..($i+5)] -replace " "
}

##########################################################################################################
#Convertir los grupos de 6 bits a decimal
Write-Host "#############################################################"
Write-Host "Convertir los grupos de 6 bits a decimal"
Write-Host "#############################################################"
##########################################################################################################
#Hay que asegurarse que todas las agrupaciones tienen 6 bits, por eso es necesario añadir bits
$bitsfaltan=([math]::Round($cadenabalmacen.Length/6)*6)-$cadenabalmacen.Length
#Si añadimos dos bits tenemos que añadir el caracter = cuando codifiquemos en Base 64 al final de la codificación
#Si añadimos cuatro bits tenemos que añadir los caracteres == cuando codifiquemos en Base 64 al final de la codificación
$espacio=""

for($i=0;$i -lt $cadenabalmacen.Length; $i=$i+6)
{
$binario=[String]$cadenabalmacen[($i)..($i+5)] -replace " "
if($binario.Length -eq 4){$binario=$binario+"00";$espacio="="}
if($binario.Length -eq 2){$binario=$binario+"0000";$espacio="=="}
$binario,[convert]::ToInt32($binario,2)
}

##########################################################################################################
#Representar el texto decimal en caracteres ASCII
Write-Host "#############################################################"
Write-Host "Representar el texto decimal en caracteres ASCII"
Write-Host "#############################################################"
##########################################################################################################
$finalcodificado=""
$cascii="ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/"
for($i=0;$i -lt $cadenabalmacen.Length; $i=$i+6)
{
$binario=[String]$cadenabalmacen[($i)..($i+5)] -replace " "
if($binario.Length -eq 4){$binario=$binario+"00";$espacio="="}
if($binario.Length -eq 2){$binario=$binario+"0000";$espacio="=="}
$finalcodificado+=$cascii[[convert]::ToInt32($binario,2)]
}
$finalcodificado+$espacio

```
