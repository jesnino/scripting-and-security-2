# Creating HTML Reports
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/16/creating-html-reports/
```PowerShell
Get-Process |ConvertTo-Html | Set-Content -Path process.html

```
