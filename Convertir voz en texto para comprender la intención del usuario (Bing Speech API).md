# Convertir voz en texto para comprender la intención del usuario (Bing Speech API)
## PowerShell, Recognition 
### URL: https://www.jesusninoc.com/2017/12/29/convertir-voz-en-texto-para-comprender-la-intencion-del-usuario-bing-speech-api/
```PowerShell
#URI del servicio de reconocimiento
$URI = 'https://speech.platform.bing.com/speech/recognition/interactive/cognitiveservices/v1?language=de-de&format=detailed'

#Cabeceras (incluir la clave del API)
$Cabeceras = @{
  'Ocp-Apim-Subscription-Key' = 'Clave del API';
  'Transfer-Encoding' = 'chunked'
  'Content-type' = 'audio/wav; codec=audio/pcm; samplerate=16000'
}

#Convertir el fichero WAV en Bytes
$AudioBytes = [System.IO.File]::ReadAllBytes("C:\Users\juan\Desktop\recono\Intro.wav")

#Preperar la petición y obtener respuesta
$Respuesta = Invoke-RestMethod -Method POST -Uri $URI -Headers $Cabeceras -Body $AudioBytes

#Convertir respuesta en formato JSON
ConvertTo-Json $Respuesta

```
