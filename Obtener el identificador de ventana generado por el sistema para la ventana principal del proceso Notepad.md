# Obtener el identificador de ventana generado por el sistema para la ventana principal del proceso Notepad
## PowerShell 
### URL: https://www.jesusninoc.com/2016/11/11/obtener-el-identificador-de-ventana-generado-por-el-sistema-para-la-ventana-principal-del-proceso-notepad/
```PowerShell
Get-Process Notepad | Select-Object Name,MainWindowHandle

```
