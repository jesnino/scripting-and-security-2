# Mostrar las etiquetas meta del head de una página web con PowerShell
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/03/16/mostrar-las-etiquetas-meta-del-head-de-una-pagina-web-con-powershell/
```PowerShell
$web=Invoke-WebRequest 'https://www.jesusninoc.com'
$web.ParsedHtml.head.getElementsByTagName('meta') | %{$_.name}

```
