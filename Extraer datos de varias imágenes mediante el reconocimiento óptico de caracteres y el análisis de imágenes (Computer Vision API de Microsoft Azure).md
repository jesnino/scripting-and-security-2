# Extraer datos de varias imágenes mediante el reconocimiento óptico de caracteres y el análisis de imágenes (Computer Vision API de Microsoft Azure)
## PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2018/01/08/extraer-datos-de-varias-imagenes-mediante-el-reconocimiento-optico-de-caracteres-y-el-analisis-de-imagenes-computer-vision-api-de-microsoft-azure/
```PowerShell
Get-ChildItem C:\Users\juan\Desktop\bodegon | %{
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
