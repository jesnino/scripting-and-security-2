# Enviar la reproducción de los tráileres de películas a la Smart TV
## Automation, Multimedia, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/11/22/enviar-la-reproduccion-de-los-traileres-de-peliculas-a-la-smart-tv/
```PowerShell
#Función para enviar la reproducción a la Smart TV
function EnviarSmartTV
{
#Importar DLL para simular el clic del ratón
#Es necesario poner las comillas correctamente cuando se importa la DLL user32.dll
 
$MouseEventSig=@’
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
‘@
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name “MouseEventWinApi” -passThru

#Depende de la resolución de pantalla
#Pulsar en "Personaliza y controla Google Chrome"
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(1347,43)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 5

#Nos posicionamos en la opción "Enviar"
[System.Windows.Forms.SendKeys]::SendWait(‘E')
Start-Sleep -Seconds 5

#Pulsar la tecla ENTER
[System.Windows.Forms.SendKeys]::SendWait(‘{ENTER}’)
Start-Sleep -Seconds 10

#Enviar youtube.com a la primera TV
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(653,153)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 5

#Pulsar en "ENVIAR"
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point(705,173)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
}

$url='https://www.youtube.com/user/UniversalSpain/playlists?sort=lad&flow=list&view=1'
$result = Invoke-WebRequest $url
#Respetar los dos espacios entre "link yt"
$result.AllElements | Where class -eq “ spf-link  yt-uix-sessionlink” | %{$_.outerText
'https://www.youtube.com'+$_.href
#Reproducir tráiler
$trailer='https://www.youtube.com'+$_.href
Start-Process chrome $trailer
#Enviar la reproducción a la Smart TV mediante la función EnviarSmartTV
EnviarSmartTV
Start-Sleep -Seconds 200
}

```
