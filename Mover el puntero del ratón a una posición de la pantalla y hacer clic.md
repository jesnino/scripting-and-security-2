# Mover el puntero del ratón a una posición de la pantalla y hacer clic
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2016/10/12/mover-el-puntero-del-raton-a-una-posicion-de-la-pantalla-y-hacer-clic/
```PowerShell
#Importar función para hacer clic
$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

#Mover el cursor del ratón a la posición 28,32
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(28,32)

#Hacer clic en la posición 28,32
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)

```
