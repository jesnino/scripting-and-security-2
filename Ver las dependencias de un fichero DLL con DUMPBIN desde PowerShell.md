# Ver las dependencias de un fichero DLL con DUMPBIN desde PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/18/ver-las-dependencias-de-un-fichero-dll-con-dumpbin-desde-powershell/
```PowerShell
# Información sobre Microsoft COFF Binary File Dumper DUMPBIN
# https://msdn.microsoft.com/es-es/library/c1h23y6c.aspx

cd "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Tools\MSVC\14.13.26128\bin\Hostx86\x86"
.\dumpbin.exe /dependents C:\Windows\System32\zipfldr.dll

```
