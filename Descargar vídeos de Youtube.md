# Descargar vídeos de Youtube
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2017/04/27/descargar-videos-de-youtube/
```PowerShell
#Leer fichero con vídeos para descargar
(Get-Content e:\descargar.txt) | %{
$_
#Utilizar el programa youtube-dl
#Descargar el programa youtube-dl desde https://github.com/rg3/youtube-dl/releases
e:\youtube-dl.exe $_
}

```
