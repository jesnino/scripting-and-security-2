# Verificar si existe un usuario en Windows 10 con PowerShell
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2017/06/24/verificar-si-existe-un-usuario-en-windows-10-con-powershell/
```PowerShell
$usuario="juan"
$existe = $(try { Get-LocalUser -Name $usuario } catch{}) -ne $null
"$usuario : $existe"

```
