# Mostrar información nutricional de un producto de consumo en el supermercado de El Corte Inglés con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/03/10/mostrar-informacion-nutricional-de-un-producto-de-consumo-en-el-supermercado-de-el-corte-ingles-con-powershell/
```PowerShell
$web = Invoke-WebRequest "https://www.elcorteingles.es/supermercado/0110120646700219-lindt-swiss-premium-chocolate-con-leche-y-avellanas-tableta-300-g/"
$web.AllElements | Where Class -eq "info _nutrients" | %{
    $_.innerText
}

```
