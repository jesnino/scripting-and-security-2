# Convertir una lista de ficheros MP4 a MP3 con FFmpeg
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2017/05/03/convertir-una-lista-de-ficheros-mp4-a-mp3-con-ffmpeg/
```PowerShell
ls *.mp4 | %{
$_.FullName
#Descargar FFmpeg https://ffmpeg.org/download.html
E:\programas\ffmpeg\bin\ffmpeg.exe -i $_.FullName -acodec libmp3lame -ab 128k $_.FullName.replace(".mp4",".mp3")
}

```
