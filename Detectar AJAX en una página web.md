# Detectar AJAX en una página web
## Automation, JavaScript, PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/10/02/detectar-ajax-en-una-pagina-web/
```PowerShell
$web=Invoke-WebRequest https://www.jesusninoc.com/
$web.AllElements | Where Class -Match “ajax” | %{$_.outerHTML}

```
