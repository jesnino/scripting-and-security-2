# Diferencia horaria entre España y Alemania
## PowerShell 
### URL: https://www.jesusninoc.com/2016/12/08/diferencia-horaria-entre-espana-y-alemania/
```PowerShell
((Get-Date)-([TimeZoneInfo]::ConvertTime((Get-Date),[TimeZoneInfo]::FindSystemTimeZoneById("Central European Standard Time")))).Hours

```
