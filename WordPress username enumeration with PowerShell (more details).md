# WordPress username enumeration with PowerShell (more details)
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/03/09/wordpress-username-enumeration-with-powershell-more-details/
```PowerShell
$id=0
while(1)
{
Start-Sleep -Seconds 2
$jsondetail=(Invoke-WebRequest -Uri ('https://www.jesusninoc.com/wp-json/wp/v2/users/'+$id)).content | ConvertFrom-JSON
$jsondetail
$id=$id+1
$jsondetail=$null
}

```
