# Crear el perfil de usuario en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/07/13/crear-el-perfil-de-usuario-en-powershell/
```PowerShell
#Para poder utilizar el fichero del perfil es necesario habilitar la ejecución de scripts
New-Item -Path $Profile.CurrentUserAllHosts -ItemType File -Force

```
