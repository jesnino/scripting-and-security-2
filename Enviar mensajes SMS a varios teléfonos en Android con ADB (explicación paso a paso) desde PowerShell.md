# Enviar mensajes SMS a varios teléfonos en Android con ADB (explicación paso a paso) desde PowerShell
## Android, Automation, PowerShell 
### URL: https://www.jesusninoc.com/2017/04/24/enviar-mensajes-sms-a-varios-telefonos-en-android-con-adb-explicacion-paso-a-paso-desde-powershell/
```PowerShell
#Entrar en la carpeta ADB
cd C:\adb

#Listar los dispositivos conectados
.\adb.exe devices

#Probar que el dispositivo funciona listando los procesos
.\adb shell ps

#Escribir un mensajes sin enviar
.\adb.exe shell am start -a android.intent.action.SENDTO -d sms:123456789 --es sms_body "Hi" --ez exit_on_sent true

#Escribir un mensajes y enviarlo
.\adb.exe shell am start -a android.intent.action.SENDTO -d sms:123456789 --es sms_body "Hi" --ez exit_on_sent true
#Pulsar en el botón de enviar que se encuentra en la posición 1000,1000
Start-Sleep -Seconds 5
.\adb shell input tap 1000 1000

#Escribir un mensaje y enviarlo a cada uno de los números que están en el fichero numeros.txt
gc .\numeros.txt | % {
$_
.\adb.exe shell am start -a android.intent.action.SENDTO -d sms:$_ --es sms_body "Hi" --ez exit_on_sent true
#Pulsar en el botón de enviar que se encuentra en la posición 1000,1000
Start-Sleep -Seconds 5
.\adb shell input tap 1000 1000
}

```
