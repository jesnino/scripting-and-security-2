# Crear un fichero de volcado de memoria de un proceso y detectar DLL
## Forensic analysis, PowerShell, Processes, Security 
### URL: https://www.jesusninoc.com/2017/10/22/crear-un-fichero-de-volcado-de-memoria-de-un-proceso-y-detectar-dll/
```PowerShell
Get-Process -Name notepad -Module | Sort-Object ModuleName

```
```PowerShell
#Crear fichero de volcado
$Proceso=Get-Process -Name notepad
$NombreF=(($Proceso).name)+'.dmp'
$Fichero = New-Object IO.FileStream($NombreF,[IO.FileMode]::Create)
(([PSObject].Assembly.GetType('System.Management.Automation.WindowsErrorReporting')).GetNestedType('NativeMethods', 'NonPublic')).GetMethod('MiniDumpWriteDump',[Reflection.BindingFlags] 'NonPublic, Static').Invoke($null, @($Proceso.Handle,$Proceso.Id,$Fichero.SafeFileHandle,[UInt32] 2,[IntPtr]::Zero,[IntPtr]::Zero,[IntPtr]::Zero))
$Fichero.Close()

```
