# Almacenar información convertida a bytes en un evento en el registro de eventos de aplicación
## PowerShell 
### URL: https://www.jesusninoc.com/2018/05/05/almacenar-informacion-convertida-a-byte-en-un-evento-en-el-registro-de-eventos-de-aplicacion/
```PowerShell
# Almacenar información convertida a byte en un evento en el registro de eventos de aplicación
# La información que vamos a almacenar en el registro de eventos es arrancar la calculadora de Windows
[System.Text.Encoding] $enc = [System.Text.Encoding]::UTF8
[byte[]] $rawdata = $enc.GetBytes('start calc')
$rawdata

# Almacenar el valor en un evento del registro de eventos
Write-EventLog Application SecurityCenter 15 -msg '"Información secreta 2"' -rd $rawdata

# Ver el valor en bytes almacenado en el registro de eventos
(Get-EventLog -LogName Application -Newest 1)
((Get-EventLog -LogName Application -Newest 1).Data)

```
