# Llamar con el valor de la aplicación calculadora (calc.exe) a cada función obtenida con DUMBIN para cada DLL (el valor de la DLL que se analiza está en una variable)
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/27/llamar-con-el-valor-de-la-aplicacion-calculadora-calc-exe-a-cada-funcion-obtenida-con-dumbin-para-cada-dll-el-valor-de-la-dll-que-se-analiza-esta-en-una-variable/
```PowerShell
# Ejecutar el siguiente script puede ocasionar problemas en Windows

# Información sobre Microsoft COFF Binary File Dumper DUMPBIN
# https://msdn.microsoft.com/es-es/library/c1h23y6c.aspx

cd "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Tools\MSVC\14.13.26128\bin\Hostx86\x86"

# Nombre de DLL que se va a analizar
$dll = "advpack.dll"

# Listar funciones exportadas de un archivo DLL con DUMPBIN desde PowerShell
$content =  .\dumpbin.exe /exports C:\Windows\System32\$dll

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
$data = $funciones.split(";").Replace(" "," ").Replace("    "," ").Replace("   "," ").Replace(" ",",") | ConvertFrom-Csv

# Llamar a cada función obtenida con DUMPBIN con el valor de la aplicación calculadora (calc.exe)
$data.name | %{$_; rundll32 $dll, $_ calc.exe; Start-Sleep -Seconds 5}

```
