# Hacer clic en una posición de la pantalla con PowerShell
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2017/11/19/hacer-clic-en-una-posicion-de-la-pantalla-con-powershell/
```PowerShell
$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@
 
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(10,10)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)

```
