# Detectar los parámetros de un formulario de contacto de WordPress con PowerShell
## Automation, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/10/08/detectar-los-parametros-de-un-formulario-de-contacto-de-wordpress-con-powershell/
```PowerShell
$resultado=(((Invoke-WebRequest 'https://www.jesusninoc.com/contact/').AllElements).where{$_.tagName -eq "form"})
$detectar=$resultado.outerHTML -split "`n" | Select-String "wpcf7-form"
$detectar

```
