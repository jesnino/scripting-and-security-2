# Listar acontecimientos históricos utilizando PowerShell
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2017/10/27/listar-acontecimientos-historicos-utilizando-powershell/
```PowerShell
$url="https://carta-natal.es/astrodata/acontecimientos/27-OCTUBRE"
$result = Invoke-WebRequest $url
$result.AllElements | Where Class -eq “row” | %{$_.innerText}

```
