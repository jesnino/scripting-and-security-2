# Convertir una web con una tabla de calorías de todos los alimentos en una tabla interactiva en PowerShell
## Automation, PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2018/05/23/convertir-una-web-con-una-tabla-de-calorias-de-todos-los-alimentos-en-una-tabla-interactiva-en-powershell/
```PowerShell
$url = "http://recetasdecocina.elmundo.es/tabla-calorias"
$result = Invoke-WebRequest $url
$objetoresult = $result.AllElements | Where tagName -eq “TR” | %{$_.outerHTML -replace "<TD width=193>","|"}
$objetoresultgrid = ($objetoresult -replace "<.*?>" -replace "`n","").trim() | %{($_)}
$objetoresultgrid | %{($_.split("|").trim())[0]}

$mostrar = foreach ($item in $objetoresultgrid)
{
    if($item -notmatch "CALORÍAS")
    {
        $item | select @{l='Producto';e={$_.split("|").trim()[0]}},@{l='Calorías';e={[Int]$_.split("|").trim()[1]}}
    }
}

$mostrar | Out-GridView

```
