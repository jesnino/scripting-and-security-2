# Ver el nivel de batería en Android con ADB
## Android 
### URL: https://www.jesusninoc.com/2017/03/04/ver-el-nivel-de-bateria-en-android-con-adb/
```PowerShell
.\adb.exe shell dmesg | Select-String "battery"
.\adb.exe shell dumpsys battery

```
