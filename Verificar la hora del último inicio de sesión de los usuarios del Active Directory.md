# Verificar la hora del último inicio de sesión de los usuarios del Active Directory
## PowerShell 
### URL: https://www.jesusninoc.com/2018/06/09/verificar-la-hora-del-ultimo-inicio-de-sesion-de-los-usuarios-del-active-directory/
```PowerShell
Get-ADUser -Filter 'Name -like "*user*"' | %{
    ($_ | Get-ADObject -Properties lastLogon).lastlogon
    $dt = [DateTime]::FromFileTime(($_ | Get-ADObject -Properties lastLogon).lastlogon)
    Write-Host $_ "last logged on at:" $dt
}

```
