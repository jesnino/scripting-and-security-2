# Monitorizar en Android con ADB
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2018/01/16/monitorizar-en-android-con-adb/
```PowerShell
.\adb shell am start -n com.android.chrome/com.google.android.apps.chrome.Main -d 'https://twitter.com/microsoft'
.\adb logcat | Select-String "chrome"

```
