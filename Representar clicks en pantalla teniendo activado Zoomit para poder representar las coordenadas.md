# Representar clicks en pantalla teniendo activado Zoomit para poder representar las coordenadas
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2018/01/17/representar-clicks-en-pantalla-teniendo-activado-zoomit-para-poder-representar-las-coordenadas/
```PowerShell
#Representar clicks en pantalla teniendo activado Zoomit para poder representar las coordenadas

$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@

$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

[System.Windows.Forms.SendKeys]::SendWait("^(2)")

while($true)
{
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point([Int](Get-Random (10..1021)),[Int](Get-Random (10..800)))
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
Start-Sleep -Seconds 5
}

```
