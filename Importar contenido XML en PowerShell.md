# Importar contenido XML en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/02/10/importar-un-contenido-xml-en-powershell/
```PowerShell
[XML]$alumnos = '<?xml version="1.0"?>
<alumnos>
	<alumno id="1">
		<usuario>juanito</usuario>
		<grupo>ventas</grupo>
		<programa>notepad</programa>
		<directorio>carpetatrabajo</directorio>
		<permisos>leer</permisos>
	</alumno>
	<alumno id="2">
		<usuario>luis</usuario>
		<grupo>ventas</grupo>
		<programa>p7zip</programa>
		<directorio>carpetatrabajo</directorio>
		<permisos>444</permisos>
	</alumno>
</alumnos>'

$alumnos.alumnos.alumno | %{
    $_.usuario
    $_.grupo
}

```
