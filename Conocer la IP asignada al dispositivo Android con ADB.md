# Conocer la IP asignada al dispositivo Android con ADB
## Android 
### URL: https://www.jesusninoc.com/2017/03/11/conocer-la-ip-asignada-al-dispositivo-android-con-adb/
```PowerShell
.\adb.exe shell netcfg | Select-String "rmnet_usb0"

```
