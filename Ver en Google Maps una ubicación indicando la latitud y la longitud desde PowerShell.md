# Ver en Google Maps una ubicación indicando la latitud y la longitud desde PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/07/27/ver-en-google-maps-una-ubicacion-indicando-la-latitud-y-la-longitud-desde-powershell/
```PowerShell
$latitud="40.4523571"
$longitud="-3.6889772"
$metros="703m"
Start-Process chrome "https://www.google.es/maps/@$latitud,$longitud,$metros/data=!3m1!1e3"

```
