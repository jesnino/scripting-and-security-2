# Listar las empresas del IBEX 35 que bajan
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/01/27/listar-las-empresas-del-ibex-35-que-bajan/
```PowerShell
$web=Invoke-WebRequest 'http://www.bolsamadrid.es/esp/aspx/Mercados/Precios.aspx?indice=ESI100000000'
$web.AllElements | Where Class -eq “DifFlBj” | %{$_.innerText}

```
