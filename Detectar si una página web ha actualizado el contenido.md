# Detectar si una página web ha actualizado el contenido
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/10/07/detectar-si-una-pagina-web-ha-actualizado-el-contenido/
```PowerShell
while(1)
{
$web=Invoke-WebRequest https://www.jesusninoc.com/2017/09/17/detectar-el-formulario-de-busquedas-de-google-y-enviar-una-busqueda-al-formulario/

if($valor -ne $web.RawContentLength)
{
$valor=$web.RawContentLength
Write-Host "Contenido actualizado" $web.RawContentLength
}
Start-Sleep -Seconds 10
}

```
