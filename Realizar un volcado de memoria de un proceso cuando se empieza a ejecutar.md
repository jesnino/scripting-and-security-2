# Realizar un volcado de memoria de un proceso cuando se empieza a ejecutar
## Forensic analysis, PowerShell, Processes, Security 
### URL: https://www.jesusninoc.com/2017/09/14/realizar-un-volcado-de-memoria-de-un-proceso-cuando-se-empieza-a-ejecutar/
```PowerShell
#Arrancar programa notepad.exe y no avisa con mensaje que se ha ejecutado
Start-Process notepad.exe .\fichero.txt

#Registrar la acción de avisar cuando se ejecuta el programa notepad.exe
#Para registrar la acción hay que ejecutar PowerShell en modo administrador
#La clase WMI del evento Win32_ProcessStartTrace indica que se ha iniciado un nuevo proceso.
Register-WMIEvent -Query "SELECT * FROM Win32_ProcessStartTrace WHERE ProcessName='notepad.exe'" -Action {
Write-Host "Nuevo proceso notepad en acción realizar volcado"
#Realizar volcado
$Proceso=Get-Process -Name notepad
$NombreF=(($Proceso).name)+'.dmp'
$Fichero = New-Object IO.FileStream($NombreF,[IO.FileMode]::Create)
(([PSObject].Assembly.GetType('System.Management.Automation.WindowsErrorReporting')).GetNestedType('NativeMethods', 'NonPublic')).GetMethod('MiniDumpWriteDump',[Reflection.BindingFlags] 'NonPublic, Static').Invoke($null, @($Proceso.Handle,$Proceso.Id,$Fichero.SafeFileHandle,[UInt32] 2,[IntPtr]::Zero,[IntPtr]::Zero,[IntPtr]::Zero))
$Fichero.Close()
} 

#Arrancar programa notepad.exe y avisa con mensaje que se ha ejecutado
Start-Process notepad.exe .\fichero.txt

```
