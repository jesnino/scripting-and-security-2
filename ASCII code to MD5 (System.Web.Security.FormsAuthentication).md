# ASCII code to MD5 (System.Web.Security.FormsAuthentication)
## PowerShell 
### URL: https://www.jesusninoc.com/2018/02/12/ascii-code-to-md5-system-web-security-formsauthentication/
```PowerShell
for($letra=0; $letra -lt 256; $letra+=1){
    #MD5
    $charc=[Char[]]$letra
    Write-Host $charc,([System.Web.Security.FormsAuthentication]::HashPasswordForStoringInConfigFile($charc, "MD5"))
}

```
