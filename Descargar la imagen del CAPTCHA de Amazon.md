# Descargar la imagen del CAPTCHA de Amazon
## PowerShell 
### URL: https://www.jesusninoc.com/2018/01/05/descargar-la-imagen-del-captcha-de-amazon/
```PowerShell
$url="https://www.amazon.es/errors/validateCaptcha"
$result = Invoke-WebRequest $url
Start-BitsTransfer ($result.Images.src | Select-String "captcha") -Destination captcha.jpg
Start-Process .\captcha.jpg

```
