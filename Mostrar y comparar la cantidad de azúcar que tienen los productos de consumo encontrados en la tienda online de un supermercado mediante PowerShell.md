# Mostrar y comparar la cantidad de azúcar que tienen los productos de consumo encontrados en la tienda online de un supermercado mediante PowerShell
## Automation, Nutrition, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/28/mostrar-y-comparar-la-cantidad-de-azucar-que-tienen-los-productos-de-consumo-encontrados-en-la-tienda-online-de-un-supermercado-mediante-powershell/
```PowerShell
$productosconurl = @{}

$web = Invoke-WebRequest "https://www.alcampo.es/compra-online/bebidas/zumos-de-frutas/naranja/c/W110201?q=%3Arelevance&show=All"

foreach($link in ($web.links.href | Group-Object).name){
    if ($link -match "compra-online/bebidas/zumos-de-frutas/naranja" -and $link -notmatch "/c/")
    {
        $urlsanalizar = "https://www.alcampo.es$link"
        $urlsanalizar
        
        $web = Invoke-WebRequest $urlsanalizar
 
        # Datos nutricionales del producto
        $productos = @{}
 
        # Extraer los valores nutricionales del producto
        ($web.AllElements | Where Class -eq “productNutritionalInformation valoresNutricionalesTabla”).innerHtml | %{
            ($_ -replace "</SPAN> <SPAN ","</SPAN>|<SPAN " -replace "<.*?>" -replace " g" -replace " Kj" -replace " Kcal" -split "`n" | ? {$_.trim() -ne ""} | ? {$_.trim() -notmatch "nutricionales"}).trim()
        } | %{$productos.add($_.split("|")[0],$_.split("|")[1])}
 
        $pesos = ($web.AllElements | Where Class -eq “productNutritionalInformation valoresNutricionalesTabla tablaInformacionAdicional”).innerText | %{
            ($_  -replace "<.*?>" -split "`n" | ? {$_.trim() -ne ""}).trim() -replace "g"
        }

        $nombre = ($web.AllElements | Where Class -eq “productDesc”).innerText | %{
            $_
        }
 
        # Añadir los valores nutricionales del producto a la estructura
        0..$pesos.Count | % {if($_%2-eq 0 -and $_ -lt 19){$productos.add($pesos[$_],$pesos[$_+1])}}
 
        # Calcular el valor nutricional en función de la cantidad del alimento consumido
        $comidacantidad = 100
 
        $productos.'Peso neto escurrido'
        $productos.Add('Valor energético(Kcal) Neto',($productos.'Valor energético(Kcal)' / $productos.'Peso Neto')*$comidacantidad)
        $productos.Add('Hidatos de carbono Neto',($productos.'Hidratos de carbono' / $productos.'Peso Neto')*$comidacantidad)
        $productos.Add('Grasas Netas',($productos.Grasas / $productos.'Peso Neto')*$comidacantidad)
        $productos.Add('Grasas saturadas Netas',($productos.'Grasas saturadas' / $productos.'Peso Neto')*$comidacantidad)
        $productos.Add('Azúcares Netos',($productos.Azúcares / $productos.'Peso Neto')*$comidacantidad)
        $productos.Add('Proteínas Netas',($productos.Proteínas / $productos.'Peso Neto')*$comidacantidad)
 
        # Mostrar la estructura con los valores nutricionales
        $productos.GetEnumerator() | sort -Property name

        $productosconurl.Add($nombre,$productos.Azúcares)
    }
}

$productosconurl.GetEnumerator() | Select-Object Key,@{n='Valor';e={[Double]($_.Value)}} | Out-GridView

```
