# Análisis de frecuencias de letras en un texto con PowerShell (parte 3)
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/01/14/analisis-de-frecuencias-de-letras-en-un-texto-con-powershell-parte-3/
```PowerShell
#Abrir el fichero texto.txt, añadir, agrupar y obtener la frecuencia de cada una de las letras que contiene el fichero a una ArrayList

#Inicializa una nueva instancia de la clase ArrayList que está vacía y tiene la capacidad inicial predeterminada
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList
 
ForEach ($elemento in [char[]](gc .\texto.txt)){
#Agrega un objeto al final de ArrayList
[void]$arraylist.Add($elemento)
}

$arraylist | Group-Object | select Name,Count

```
