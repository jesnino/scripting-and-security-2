# Converting Hash Tables to JSON
## PowerShell 
### URL: https://www.jesusninoc.com/2017/11/18/converting-hash-tables-to-json/
```PowerShell
$hash = @{
    Name = 'Jesusninoc'
    ID = 66
    Path = 'www.jesusninoc.com'
} 
$object = [PSCustomObject]$hash
$json = $object | ConvertTo-Json
$json

```
