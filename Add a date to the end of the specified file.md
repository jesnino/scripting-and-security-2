# Add a date to the end of the specified file
## PowerShell 
### URL: https://www.jesusninoc.com/2017/08/10/add-a-date-to-the-end-of-the-specified-file/
```PowerShell
Add-Content -Path .\fichero.txt -Value (Get-Date) -PassThru

```
