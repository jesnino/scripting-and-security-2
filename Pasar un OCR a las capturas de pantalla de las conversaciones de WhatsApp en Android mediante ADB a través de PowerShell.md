# Pasar un OCR a las capturas de pantalla de las conversaciones de WhatsApp en Android mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/11/07/pasar-un-ocr-a-las-capturas-de-pantalla-de-las-conversaciones-de-whatsapp-en-android-mediante-adb-a-traves-de-powershell/
```PowerShell
#Abrir WhatsApp en Android mediante ADB
#Es necesario habilitar el modo depuración en Android
cd "D:\program\android-sdk-windows\platform-tools"
.\adb.exe shell am start -n com.whatsapp/.Main
Start-Sleep -Seconds 5
#Ir avanzando por las conversaciones
$avanzar=0
do
{
.\adb shell input keyevent KEYCODE_PAGE_DOWN
Start-Sleep -Seconds 5
#Realizar una captura después de avanzar por las conversaciones
$screencap="screencap"+$avanzar+".png"
.\adb shell screencap -p /sdcard/$screencap
.\adb pull /sdcard/$screencap
.\adb shell rm /sdcard/$screencap
Start-Sleep -Seconds 2
$screencapOCR="screencap"+$avanzar+".txt"
#Pasar el OCR a la captura y guardar el texto procesado
#Es necesario descar el OCR Tesseract Open Source OCR Engine: https://github.com/tesseract-ocr
D:\Tesseract-OCR\tesseract.exe $screencap $screencapOCR
$avanzar+=1

```
