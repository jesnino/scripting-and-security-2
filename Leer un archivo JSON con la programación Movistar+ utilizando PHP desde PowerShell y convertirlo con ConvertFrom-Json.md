# Leer un archivo JSON con la programación Movistar+ utilizando PHP desde PowerShell y convertirlo con ConvertFrom-Json
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2018/05/28/leer-un-archivo-json-con-la-programacion-movistar-utilizando-php-desde-powershell/
```PowerShell
cd C:\xampp\php

$programacion = '<?php $url = "http://akamaicache.dof6.com/vod/yomvi.svc/samsung_tizen/profiles/OTT/channels?parentalRating=M18&showNonRated=true";
$json = file_get_contents($url);
echo $json;?>' | .\php.exe | ConvertFrom-Json
$programacion | select Nombre,@{Name="Titulo";Expression={$_.pases.titulo}} | Out-GridView

```
