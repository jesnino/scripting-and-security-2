# Utilizar Runspaces en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/01/19/utilizar-runspaces-en-powershell/
```PowerShell
#Crear Runspace
#Runspace crea un hilo en el proceso existente
$Runspace = [runspacefactory]::CreateRunspace()
#Es necesario crear una instancia de PowerShell para ejecutar Runspace
$PowerShell = [powershell]::Create()
$PowerShell.runspace = $Runspace
$Runspace.Open()
[void]$PowerShell.AddScript({
    Get-Date
    Start-Sleep -Seconds 10
})
$AsyncObject = $PowerShell.BeginInvoke()
#Ver si se ha completado o no la instancia
$AsyncObject | Select-Object IsCompleted
#Finalizar la instancia
$PowerShell.EndInvoke($AsyncObject)

```
