# Obtener los nombres de las funciones exportadas de un archivo DLL con DUMPBIN desde PowerShell (explicación paso a paso del script)
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/21/obtener-los-nombres-de-las-funciones-exportadas-de-un-archivo-dll-con-dumpbin-desde-powershell-explicacion-paso-a-paso-del-script/
```PowerShell
# Información sobre Microsoft COFF Binary File Dumper DUMPBIN
# https://msdn.microsoft.com/es-es/library/c1h23y6c.aspx

cd "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Tools\MSVC\14.13.26128\bin\Hostx86\x86"

# Listar funciones exportadas de un archivo DLL con DUMPBIN desde PowerShell
$content =  .\dumpbin.exe /exports C:\Windows\System32\zipfldr.dll

# Procesar la información para obtener únicamente las funciones
# Quitar líneas sin contenido
$content = ($content | ? {$_.trim() -ne "" }).trim()
# Crear un string de toda la información para poder extraer el contenido de las funciones
$all = ""
$content | %{$all = $all + $_ + ";"}
# Extraer el contenido de las funciones
$start = $all.indexof("ordinal hint RVA      name;")
$end = $all.indexof("Summary")
$length = $end - $start
$funciones = $all.substring($start, $length).replace("Summary","")

# Con el contenido de las funciones extraer el nombre de las funciones
# Convertir un array a CSV con PowerShell
# ES POSIBLE QUE HAYA QUE AÑADIR OTRAS COMBINACIONES DE ESPACIOS
$data = $funciones.split(";").Replace(" "," ").Replace(" "," ").Replace(" "," ").Replace(" ",",") | ConvertFrom-Csv

# Mostrar el nombre de las funciones
$data.name

```
```PowerShell
# Información sobre Microsoft COFF Binary File Dumper DUMPBIN
# https://msdn.microsoft.com/es-es/library/c1h23y6c.aspx

cd "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Tools\MSVC\14.13.26128\bin\Hostx86\x86"

# Listar funciones exportadas de un archivo DLL con DUMPBIN desde PowerShell
$content =  .\dumpbin.exe /exports C:\Windows\System32\zipfldr.dll

```
```PowerShell
# Procesar la información para obtener únicamente las funciones
# Quitar líneas sin contenido
$content = ($content | ? {$_.trim() -ne "" }).trim()

```
```PowerShell
# Crear un string de toda la información para poder extraer el contenido de las funciones
$all = ""
$content | %{$all = $all + $_ + ";"}
# Extraer el contenido de las funciones
$start = $all.indexof("ordinal hint RVA      name;")
$end = $all.indexof("Summary")
$length = $end - $start
$funciones = $all.substring($start, $length).replace("Summary","")

```
```PowerShell
# Con el contenido de las funciones extraer el nombre de las funciones
# Convertir un array a CSV con PowerShell
# ES POSIBLE QUE HAYA QUE AÑADIR OTRAS COMBINACIONES DE ESPACIOS
$data = $funciones.split(";").Replace(" "," ").Replace(" "," ").Replace(" "," ").Replace(" ",",") | ConvertFrom-Csv
# Mostrar el nombre de las funciones
$data.name

```
