# Extraer datos de varias imágenes de un vídeo MP4 mediante el reconocimiento óptico de caracteres y el análisis de imágenes (Computer Vision API de Microsoft Azure)
## PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2018/01/11/extraer-datos-de-varias-imagenes-de-un-video-mp4-mediante-el-reconocimiento-optico-de-caracteres-y-el-analisis-de-imagenes-computer-vision-api-de-microsoft-azure/
```PowerShell
#Dividir un vídeo MP4 en imágenes
E:\programas\ffmpeg-20161204-1f5630a-win64-static\bin\ffmpeg.exe -i capturas.mp4 -f image2 -pix_fmt bgr8 %01d.jpg

#Analizar las imágenes mediante el reconocimiento óptico de caracteres y el análisis de imágenes (Computer Vision API de Microsoft Azure)
ls *.jpg | %{
    $vision = 'https://westcentralus.api.cognitive.microsoft.com/vision/v1.0/analyze'
    $features = 'Categories,Tags,Description,Color'
    $bytes = [System.IO.File]::ReadAllBytes($_.FullName)

    $response = Invoke-WebRequest `
         -Uri "$($vision)?visualFeatures=$($features)" `
         -Body $bytes `
         -ContentType "application/octet-stream" `
         -Headers @{'Ocp-Apim-Subscription-Key' = 'Clave del API'} `
         -Method 'Post' `
         -ErrorAction Stop `
         -UseBasicParsing | ConvertFrom-Json

    $response.description
    Start-Sleep -Seconds 5
}

```
