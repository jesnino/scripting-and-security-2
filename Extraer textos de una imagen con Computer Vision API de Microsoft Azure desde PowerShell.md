# Extraer textos de una imagen con Computer Vision API de Microsoft Azure desde PowerShell
## PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2017/01/03/extraer-textos-de-imagenes-con-computer-vision-api-de-microsoft-azure-desde-powershell/
```PowerShell
$vision = 'https://westcentralus.api.cognitive.microsoft.com/vision/v1.0/ocr'
$bytes = [System.IO.File]::ReadAllBytes("C:\Users\juan\Desktop\Negocios.png")

$response = Invoke-WebRequest `
     -Uri $vision `
     -Body $bytes `
     -ContentType "application/octet-stream" `
     -Headers @{'Ocp-Apim-Subscription-Key' = 'Clave del API'} `
     -Method 'Post' `
     -ErrorAction Stop `
     -UseBasicParsing | ConvertFrom-Json

$response | Format-Custom

```
