# Reconocer emociones de las caras de las personas que hay en una imagen con Emotion API de Microsoft Azure
## PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2018/01/12/reconocer-emociones-de-las-caras-de-las-personas-que-hay-en-una-imagen-con-emotion-api-de-microsoft-azure/
```PowerShell
$vision = 'https://westus.api.cognitive.microsoft.com/emotion/v1.0/recognize?'
$bytes = [System.IO.File]::ReadAllBytes("C:\Users\juan\Desktop\recono\mayores.jpg")

$response = Invoke-WebRequest `
     -Uri "$($vision)" `
     -Body $bytes `
     -ContentType "application/octet-stream" `
     -Headers @{'Ocp-Apim-Subscription-Key' = 'Clave del API'} `
     -Method 'Post' `
     -ErrorAction Stop `
     -UseBasicParsing | ConvertFrom-Json

$response | Format-Custom

```
