# Calcular la información nutricional neta de un producto de consumo con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/02/27/calcular-la-informacion-nutricional-neta-de-un-producto-de-consumo-con-powershell/
```PowerShell
$web = Invoke-WebRequest "https://www.alcampo.es/compra-online/productos-frescos/pescados-y-mariscos/anchoas-y-boquerones/anchoas/consorcio-anchoa-en-aceite-de-oliva-29-gramos/p/60139"

$productos = @{}

($web.AllElements | Where Class -eq “productNutritionalInformation valoresNutricionalesTabla”).innerHtml | %{
    ($_ -replace "</SPAN> <SPAN ","</SPAN>|<SPAN " -replace "<.*?>" -replace " g" -replace " Kj" -replace " Kcal" -split "`n" | ? {$_.trim() -ne ""} | ? {$_.trim() -notmatch "nutricionales"}).trim()
} | %{$productos.add($_.split("|")[0],$_.split("|")[1])}

$pesos = ($web.AllElements | Where Class -eq “productNutritionalInformation valoresNutricionalesTabla tablaInformacionAdicional”).innerText | %{
    ($_  -replace "<.*?>" -split "`n" | ? {$_.trim() -ne ""}).trim() -replace "g"
}

0..$pesos.Count | % {if($_%2-eq 0 -and $_ -lt 19){$productos.add($pesos[$_],$pesos[$_+1])}}

$productos.'Peso neto escurrido'
$productos.add('Valor energético(Kcal) Neto',($productos.'Valor energético(Kcal)' / 100)*$productos.'Peso neto escurrido')
$productos.add('Hidatos de carbono Neto',($productos.'Hidratos de carbono' / 100)*$productos.'Peso neto escurrido')
$productos.add('Grasas Netas',($productos.Grasas / 100)*$productos.'Peso neto escurrido')
$productos.add('Grasas saturadas Netas',($productos.'Grasas saturadas' / 100)*$productos.'Peso neto escurrido')
$productos.add('Azúcares Netos',($productos.Azúcares / 100)*$productos.'Peso neto escurrido')
$productos.add('Proteínas Netas',($productos.Proteínas / 100)*$productos.'Peso neto escurrido')

$productos.GetEnumerator() | sort -Property name

```
