# Usar ADB sobre red
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2017/02/19/usar-adb-sobre-red/
```PowerShell
#Es necesario tener acivado en el móvil la opción "ADB sobre red"
#También hay que permitir la depuración USB
$device="192.168.1.156:5555"
.\adb connect $device

```
