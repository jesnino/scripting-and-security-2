# Enviar un mensaje SMS en Android con ADB (pulsando en la posición del botón enviar)
## Android, Automation, PowerShell 
### URL: https://www.jesusninoc.com/2017/04/19/enviar-un-mensaje-sms-en-android-con-adb-pulsando-en-la-posicion-del-boton-enviar/
```PowerShell
#Escribir un mensajes y enviarlo
.\adb.exe shell am start -a android.intent.action.SENDTO -d sms:123456789 --es sms_body "Hi" --ez exit_on_sent true
#Pulsar en el botón de enviar que se encuentra en la posición 1000,1000
Start-Sleep -Seconds 5
.\adb shell input tap 1000 1000

```
