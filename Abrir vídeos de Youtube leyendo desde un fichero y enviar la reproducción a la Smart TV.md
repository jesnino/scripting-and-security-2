# Abrir vídeos de Youtube leyendo desde un fichero y enviar la reproducción a la Smart TV
## Automation, Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2016/11/26/abrir-videos-de-youtube-leyendo-desde-un-fichero-y-enviar-la-reproduccion-a-la-smart-tv/
```PowerShell
#El fichero contiene enlaces de Yotube
#https://www.youtube.com/watch?v=sNwpQwn5awY
#https://www.youtube.com/watch?v=ETradti7L4c

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

Get-Content E:\listadovideos.txt | % {
#Abrir enlace de Youtube
Start-Process chrome $_
#Enviar la reproducción a la Smart TV mediante la función EnviarSmartTV
EnviarSmartTV
#Esperar antes de reproducir el siguiente vídeo
Start-Sleep -Seconds 200
}

```
