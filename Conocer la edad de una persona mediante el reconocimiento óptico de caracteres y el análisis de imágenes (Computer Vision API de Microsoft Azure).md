# Conocer la edad de una persona mediante el reconocimiento óptico de caracteres y el análisis de imágenes (Computer Vision API de Microsoft Azure)
## PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2018/01/14/conocer-la-edad-de-una-persona-mediante-el-reconocimiento-optico-de-caracteres-y-el-analisis-de-imagenes-computer-vision-api-de-microsoft-azure/
```PowerShell
#URI del servicio de reconocimiento
$URI = 'https://westcentralus.api.cognitive.microsoft.com/vision/v1.0/analyze'

#Caracteristicas que serán analizadas
$features = 'Categories,Faces'

#Caberas (incluir la clave del API)
$Cabeceras = @{
  'Ocp-Apim-Subscription-Key' = 'Clave del API';
  'Content-type' = 'application/json'
}

#URL de la imagen
$Body = '{"url":"https://www.windowscentral.com/sites/wpcentral.com/files/styles/large/public/topic_images/2014/Topic_Page_Satya_Nadella.jpg?itok=X5a6zYjg"}'

#Preperar la petición y obtener respuesta
$Respuesta = Invoke-RestMethod -Method Post -Uri ($URI+"?visualFeatures=$($features)") -Headers $Cabeceras -Body $Body

#Convertir respuesta en formato JSON y obtener la edad de la persona de la imagen
ConvertTo-Json $Respuesta.faces.age

```
