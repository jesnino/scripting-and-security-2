# Crear un fichero de volcado de memoria de un proceso y buscar una cadena
## Forensic analysis, PowerShell, Processes, Security 
### URL: https://www.jesusninoc.com/2017/09/12/crear-un-fichero-de-volcado-de-memoria-de-un-proceso-y-buscar-una-cadena/
```PowerShell
$Proceso=Get-Process -Name notepad
$NombreF=(($Proceso).name)+'.dmp'
$Fichero = New-Object IO.FileStream($NombreF,[IO.FileMode]::Create)
(([PSObject].Assembly.GetType('System.Management.Automation.WindowsErrorReporting')).GetNestedType('NativeMethods', 'NonPublic')).GetMethod('MiniDumpWriteDump',[Reflection.BindingFlags] 'NonPublic, Static').Invoke($null, @($Proceso.Handle,$Proceso.Id,$Fichero.SafeFileHandle,[UInt32] 2,[IntPtr]::Zero,[IntPtr]::Zero,[IntPtr]::Zero))
$Fichero.Close()

```
