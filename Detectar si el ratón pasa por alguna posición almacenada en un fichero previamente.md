# Detectar si el ratón pasa por alguna posición almacenada en un fichero previamente
## Automation, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/01/18/detectar-si-el-raton-pasa-por-alguna-posicion-almacenada-en-un-fichero-previamente/
```PowerShell
#Inicializa una nueva instancia de la clase ArrayList que está vacía y tiene la capacidad inicial predeterminada
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList
 
ForEach ($elemento in gc .\posicion.txt){
#Agrega un objeto al final de ArrayList
[void]$arraylist.Add($elemento)
}

for (1)
{
Start-Sleep -s 2
$dY = ([System.Windows.Forms.Cursor]::Position.Y)
$dX = ([System.Windows.Forms.Cursor]::Position.X)
Write-Host $dX,$dY
if($arraylist.IndexOf("$dX,$dY") -eq -1)
{
"Elemento no encontrado"
}
else
{
'Elemento encontrado en la posición ' + $arraylist.IndexOf("$dX,$dY")
}
}

```
