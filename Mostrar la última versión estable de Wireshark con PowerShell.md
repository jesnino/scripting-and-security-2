# Mostrar la última versión estable de Wireshark con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/29/mostrar-la-ultima-version-estable-de-wireshark-con-powershell/
```PowerShell
([xml] [System.Net.WebClient]::new().DownloadString('https://www.wireshark.org/update/0/Wireshark/2.2.2/Windows/x86/en-US/stable.xml')).RSS.Channel.Item | Format-Table title,releaseNotesLink

```
