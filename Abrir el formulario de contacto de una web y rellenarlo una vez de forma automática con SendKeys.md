# Abrir el formulario de contacto de una web y rellenarlo una vez de forma automática con SendKeys
## PowerShell, Web 
### URL: https://www.jesusninoc.com/2016/11/01/abrir-el-formulario-de-contacto-de-una-web-y-rellenarlo-una-vez-de-forma-automatica-con-sendkeys/
```PowerShell
#Función necesaria para hacer clic en una parte de la página
$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@
$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

#Abrir la web de contacto
Start-Process chrome "https://www.jesusninoc.com/contact2/"

#Pulsar en cualquier parte de la web para poner el foco dentro
Start-Sleep -Seconds 2
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(833,189)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)

#Ir tabulando y escribiendo en los campos del formulario
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
[System.Windows.Forms.SendKeys]::SendWait('Bob')
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
[System.Windows.Forms.SendKeys]::SendWait('Esponja')
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
[System.Windows.Forms.SendKeys]::SendWait('12345')
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
[System.Windows.Forms.SendKeys]::SendWait('bob@esponja.com')
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
[System.Windows.Forms.SendKeys]::SendWait(' ')

#Una vez cumplimentados los campos pulsar ENTER
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait('{TAB}')
[System.Windows.Forms.SendKeys]::SendWait("{ENTER}")

```
