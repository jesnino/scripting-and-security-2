# Leer un archivo JSON con la programación Movistar+ desde PowerShell
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/18/leer-un-archivo-json-con-la-programacion-movistar-desde-powershell/
```PowerShell
$Comienzo = Get-Date # Calcular el tiempo de carga del fichero JSON

$web = Invoke-WebRequest "https://www.jesusninoc.com/s/movistar.php"

$Tiempo = ((Get-Date) - $Comienzo).TotalMilliseconds;$Tiempo # Calcular el tiempo de carga del fichero JSON

$json = $web.content | ConvertFrom-Json 
$json | select Nombre,@{Name="Titulo";Expression={$_.pases.titulo}} | Out-GridView

```
