# Mostrar los títulos de las noticias de una página web
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2018/05/17/mostrar-los-titulos-de-las-noticias-de-una-pagina-web/
```PowerShell
$url = "https://www.jesusninoc.com/"
$result = Invoke-WebRequest $url
#La etiqueta que tenemos buscar es: class="entry-title"
$result.AllElements | Where Class -eq “entry-title” | %{$_.innerText}

```
