# Conectarse a una carpeta compartida con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/06/14/conectarse-a-una-carpeta-compartida-con-powershell/
```PowerShell
$rutacarpetacompartida = '\\equipo\carpetacompartida'
 
net use * $rutacarpetacompartida
New-PSDrive -Name q -PSProvider FileSystem -Root $rutacarpetacompartida -Persist
New-SmbMapping -LocalPath 'q:' -RemotePath  $rutacarpetacompartida

```
