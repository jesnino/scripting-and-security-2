# Verificar si existe una unidad organizativa con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/06/18/verificar-si-existe-una-unidad-organizativa-con-powershell/
```PowerShell
$OUruta = 'OU=Unidad,DC=dominio,DC=local'
$existe = $(try { Get-ADOrganizationalUnit -Identity $OUruta -ErrorAction Ignore } catch{}) -ne $null
"$OUruta : $existe"

```
