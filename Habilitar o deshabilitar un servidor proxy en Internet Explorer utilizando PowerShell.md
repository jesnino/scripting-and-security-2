# Habilitar o deshabilitar un servidor proxy en Internet Explorer utilizando PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/03/27/habilitar-o-deshabilitar-un-servidor-proxy-en-internet-explorer-utilizando-powershell/
```PowerShell
Set-ItemProperty 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Internet Settings' -Name ProxyEnable -Value 1

```
```PowerShell
Set-ItemProperty 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Internet Settings' -Name ProxyEnable -Value 0

```
