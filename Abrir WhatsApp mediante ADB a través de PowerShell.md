# Abrir WhatsApp mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/30/abrir-whatsapp-mediante-adb-a-traves-de-powershell/
```PowerShell
#Abrir WhatsApp en Android mediante ADB
#Es necesario habilitar el modo depuración en Android
cd "D:\program\android-sdk-windows\platform-tools"
.\adb.exe shell am start -n com.whatsapp/.Main
Start-Sleep -Seconds 5

```
