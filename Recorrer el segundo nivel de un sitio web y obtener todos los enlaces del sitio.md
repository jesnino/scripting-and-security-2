# Recorrer el segundo nivel de un sitio web y obtener todos los enlaces del sitio
## Automation, PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/12/05/recorrer-el-segundo-nivel-de-un-sitio-web-y-obtener-todos-los-enlaces-del-sitio/
```PowerShell
$url="http://www.jesusninoc.com"
foreach($links in (Invoke-WebRequest $url).Links.href){foreach($links2 in (Invoke-WebRequest $links).Links.href){$links2}}

```
