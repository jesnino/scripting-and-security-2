# Detectar el formulario de búsquedas de Google y enviar una búsqueda al formulario
## Automation, PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/09/17/detectar-el-formulario-de-busquedas-de-google-y-enviar-una-busqueda-al-formulario/
```PowerShell
$form=(((Invoke-WebRequest 'https://www.google.com').AllElements).where{$_.tagName -eq "form"})
$Params = @{'q'='jesusninoc'}
$url='https://www.google.com/'+$form.action
$web=Invoke-WebRequest -Uri $url -Method GET -Body $Params
$web.Links

```
