# Resolver el CAPTCHA de Amazon
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2018/01/06/resolver-el-captcha-de-amazon/
```PowerShell
#Descargar la imagen del CAPTCHA de Amazon
$url="https://www.amazon.es/errors/validateCaptcha"
$result = Invoke-WebRequest $url
Start-BitsTransfer ($result.Images.src | Select-String "captcha") -Destination captcha.jpg
Start-Process .\captcha.jpg

#Convertir la imagen CAPTCHA a texto (el resultado obtenido no es positivo en la mayoría de las ocasiones)
#Tesseract OCR
#Tesseract is probably the most accurate open source OCR engine available. Combined with the Leptonica Image Processing Library it can read a wide variety of image formats and convert them to text in over 60 languages. It was one of the top 3 engines in the 1995 UNLV Accuracy test. Between 1995 and 2006 it had little work done on it, but since then it has been improved extensively by Google. It is released under the Apache License 2.0.
E:\programas\Tesseract-OCR\tesseract.exe .\captcha.jpg captcha
gc .\captcha.txt

```
