# Abrir WhatsApp y avanzar en las conversaciones mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/11/03/abrir-whatsapp-y-avanzar-en-las-conversaciones-mediante-adb-a-traves-de-powershell/
```PowerShell
#Abrir WhatsApp en Android mediante ADB
#Es necesario habilitar el modo depuración en Android
cd "D:\program\android-sdk-windows\platform-tools"
.\adb.exe shell am start -n com.whatsapp/.Main
Start-Sleep -Seconds 5
#Ir avanzando en las conversaciones
$avanzar=0
do
{
.\adb shell input keyevent KEYCODE_PAGE_DOWN
Start-Sleep -Seconds 5
$avanzar+=1
}while($avanzar -lt 10)

```
