# Obtener los perfiles que hay en Windows con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/03/02/obtener-los-perfiles-que-hay-en-windows-con-powershell/
```PowerShell
Get-CimInstance -Class Win32_UserProfile | %{([Security.Principal.SecurityIdentifier]$_.SID).Translate([Security.Principal.NTAccount]).Value}

```
