# Obtener la longitud del contenido sin formato que contiene una respuesta web
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/09/30/obtener-la-longitud-del-contenido-sin-formato-que-contiene-una-respuesta-web/
```PowerShell
$web=Invoke-WebRequest https://www.jesusninoc.com
$web.RawContentLength

```
