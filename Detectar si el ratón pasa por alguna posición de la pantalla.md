# Detectar si el ratón pasa por alguna posición de la pantalla
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2018/02/06/detectar-si-el-raton-pasa-por-alguna-posicion-de-la-pantalla/
```PowerShell
#Inicializa una nueva instancia de la clase ArrayList que está vacía y tiene la capacidad inicial predeterminada
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList

#Añadir posiciones 
[void]$arraylist.Add('0,0')


for (1)
{
    $dY = ([System.Windows.Forms.Cursor]::Position.Y)
    $dX = ([System.Windows.Forms.Cursor]::Position.X)
    if($arraylist.IndexOf("$dX,$dY") -ne -1)
    {
        "El ratón ha pasado por la posición $dX,$dY"
    }
    else
    {
        ""
    }
}

```
