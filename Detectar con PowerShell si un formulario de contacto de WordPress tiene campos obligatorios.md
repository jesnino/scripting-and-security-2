# Detectar con PowerShell si un formulario de contacto de WordPress tiene campos obligatorios
## PowerShell, Security, Web, Web scraping 
### URL: https://www.jesusninoc.com/2017/10/06/detectar-con-powershell-si-un-formulario-de-contacto-de-wordpress-tiene-campos-obligatorios/
```PowerShell
$resultado=(((Invoke-WebRequest 'https://www.jesusninoc.com/contact/').AllElements).where{$_.tagName -eq "form"})
$resultado.outerHTML | Select-String "as-required"
$resultado.outerHTML -split "`n" | Select-String "as-required"

```
