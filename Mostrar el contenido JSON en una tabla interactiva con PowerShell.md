# Mostrar el contenido JSON en una tabla interactiva con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/30/mostrar-el-contenido-json-en-una-tabla-interactiva-con-powershell/
```PowerShell
(Invoke-WebRequest -Uri https://api.spacexdata.com/v2/launches/latest -UseBasicParsing).Content | ConvertFrom-Json | Out-GridView

```
