# Conocer la relevancia de una búsqueda en Bing
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/05/15/conocer-la-relevancia-de-una-busqueda-en-bing/
```PowerShell
$urls='https://www.bing.com/search?q=powershell'
$result=Invoke-WebRequest $urls
$valor=($result.AllElements | ? {$_.class -eq “sb_count”}).innerText
$valor
$valor=$valor.replace(".","").replace("resultados","")

switch([Int]$valor)
{
    {$_ -ge 0 -and $_ -le 1000}{"Poco importante"}
    {$_ -ge 1001 -and $_ -le 10000}{"Algo importante"}
    {$_ -ge 10000 -and $_ -le 100000000}{"Muy importante"}
}

```
