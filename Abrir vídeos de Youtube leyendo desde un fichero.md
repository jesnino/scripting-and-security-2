# Abrir vídeos de Youtube leyendo desde un fichero
## PowerShell 
### URL: https://www.jesusninoc.com/2016/11/24/abrir-videos-de-youtube-leyendo-desde-un-fichero/
```PowerShell
#El fichero contiene enlaces de Yotube
#https://www.youtube.com/watch?v=sNwpQwn5awY
#https://www.youtube.com/watch?v=ETradti7L4c

Get-Content E:\listadovideos.txt | % {
#Abrir enlace de Youtube
Start-Process chrome $_
#Esperar antes de reproducir el siguiente vídeo
Start-Sleep -Seconds 200
}

```
