# Obtener empresas del IBEX 35 en formato JSON
## PowerShell 
### URL: https://www.jesusninoc.com/2018/03/13/obtener-empresas-del-ibex-35-en-formato-json/
```PowerShell
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList

# Obtener empresas del IBEX 35
$web = Invoke-WebRequest 'http://www.bolsamadrid.es/esp/aspx/Mercados/Precios.aspx?indice=ESI100000000'
$result = $web.AllElements | Where Class -eq “DifFlBj” | %{$_.innerText}
$result += $web.AllElements | Where Class -eq “DifFlSb” | %{$_.innerText}
$result += $web.AllElements | Where Class -eq “DifFlIg” | %{$_.innerText}

# Almacenar en un array cada empresa del IBEX 35
ForEach ($elemento in $result){
    $null = $arraylist.Add(
    [pscustomobject] @{
    Empresa = $elemento
    Cotización = 0
    }
)
}

# Eliminar el primer elemento del array porque contiene una empresa no válida
$arraylist.Removeat(0)
# Número de empresas, tiene que ser 35
$arraylist.Count

# Convertir a JSON
$json = $arraylist | ConvertTo-Json

# Importar el contenido JSON y listar las empresas
($json | ConvertFrom-Json).empresa

```
