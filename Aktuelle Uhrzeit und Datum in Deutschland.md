# Aktuelle Uhrzeit und Datum in Deutschland
## PowerShell 
### URL: https://www.jesusninoc.com/2017/02/05/aktuelle-uhrzeit-und-datum-in-deutschland/
```PowerShell
[TimeZoneInfo]::ConvertTime((Get-Date),[TimeZoneInfo]::FindSystemTimeZoneById("Central European Standard Time"))

```
