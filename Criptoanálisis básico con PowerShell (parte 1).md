# Criptoanálisis básico con PowerShell (parte 1)
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/01/05/criptoanalisis-basico-con-powershell-parte-1/
```PowerShell
#Realizar un criptoanálisis básico para descifrar un texto, decrementar valores a cada letra
#Descifrar la cadena lj|j
$descifrar="lj|j"

#Añadir un diccionario a una ArrayList
#Inicializa una nueva instancia de la clase ArrayList que está vacía y tiene la capacidad inicial predeterminada
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList
ForEach ($elemento in gc .\diccionario.txt){
#Agrega un objeto al final de ArrayList
[void]$arraylist.Add($elemento)
}

#Realizar una operación sobre cada uno de los caracteres que componen la cadena cifrada
for($var=0;$var -lt 20;$var=$var+1){
$textodescifrado=(0..($descifrar.Length-1) | % {[char]::ConvertFromUtf32([char]::ConvertToUtf32($descifrar[$_].ToString(),0)-$var)}) -join ""
#Una vez se le ha aplicado la operación a la palabra comprobamos resultante se encuentra en un diccionario
if($arraylist.IndexOf($textodescifrado) -eq -1){"Elemento: $textodescifrado no encontrado"}
else{"Elemento $textodescifrado encontrado en la posición " + $arraylist.IndexOf($textodescifrado)}
}

```
