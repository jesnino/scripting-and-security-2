# Automatizar el recorrido de niveles de un sitio web, obteniendo información de todos los enlaces del sitio y añadir la información creando una clase a un array
## Automation, PowerShell, Web 
### URL: https://www.jesusninoc.com/2017/12/15/automatizar-el-recorrido-de-niveles-de-un-sitio-web-obteniendo-informacion-de-todos-los-enlaces-del-sitio-y-anadir-la-informacion-creando-una-clase-a-un-array/
```PowerShell
#Clase Enlace con información sobre el enlace: URL, tamaño y nivel de recorrido
class Enlace
{ 
    $URL
    $Long
    $Level

    Enlace($URL,$Long,$Level)
    {
        $this.URL=$URL
        $this.Long=$Long
        $this.Level=$Level
    }
}

#Iniciar array
$myArray = @()
$myArray += [Enlace]::new("https://www.jesusninoc.com/",1,1)

#Eliminar el fichero que contiene la expresión que se va a ejecutar
rm .\fichero.txt
"" | Out-File -FilePath fichero.txt -NoNewline

#Crear una función que permite automatizar el recorrido de una web por niveles
$url="https://www.jesusninoc.com/"
function insertar($numeroveces)
{
for($i;$i -lt $numeroveces;$i++){'foreach($links'+($i+1)+' in (Invoke-WebRequest $links'+$i+').Links.href){' | Add-Content -Path fichero.txt -NoNewline}
'if(!$myArray.URL.Contains($links'+$numeroveces+')){$myArray += [Enlace]::new($links'+$numeroveces | Add-Content -Path fichero.txt -NoNewline
',(Invoke-WebRequest $links'+$numeroveces+').RawContentLength,' | Add-Content -Path fichero.txt -NoNewline
$numeroveces | Add-Content -Path fichero.txt -NoNewline
')' | Add-Content -Path fichero.txt -NoNewline
';start-sleep -s 2' | Add-Content -Path fichero.txt -NoNewline
';$links'+$numeroveces | Add-Content -Path fichero.txt -NoNewline
'}' | Add-Content -Path fichero.txt -NoNewline
for($j;$j -lt $numeroveces;$j++){"}" | Add-Content -Path fichero.txt -NoNewline}
}

#Ejecutar la función y leer la información que ha generado la función
insertar(1)
gc .\fichero.txt

#Ejecutar la expresión generada al ejecutar la función que permite automatizar el recorrido de una web por niveles
foreach($links in (Invoke-WebRequest $url).Links.href){Invoke-Expression(gc .\fichero.txt)}

#Ordenar el array por tamaño
$myArray | sort Long

```
