# Detectar el formulario de búsquedas de Yahoo y enviar una búsqueda al formulario
## Automation, PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/09/23/detectar-el-formulario-de-busquedas-de-yahoo-y-enviar-una-busqueda-al-formulario/
```PowerShell
$form=(((Invoke-WebRequest 'https://es.yahoo.com/').AllElements).where{$_.tagName -eq "form"})
$form.action
$Params = @{'p'='jesusninoc'}
$web=Invoke-WebRequest -Uri $form.action -Method $form.method -Body $Params
$web.Links

```
