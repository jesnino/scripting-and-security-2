# Crear una notificación en Windows con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2017/11/23/crear-una-notificacion-en-windows-con-powershell/
```PowerShell
$balloon = New-Object System.Windows.Forms.NotifyIcon 

#Configurar notificación
#Icono
$balloon.Icon  = [System.Drawing.Icon]::ExtractAssociatedIcon((Get-Process -Name notepad).Path) 
$balloon.BalloonTipIcon  = [string]$Icon = 'Info'
#Mensaje
$balloon.BalloonTipText  = "Mensaje"
#Título
$balloon.BalloonTipTitle  = "Título"
 
$balloon.Visible  = $true
$balloon.ShowBalloonTip(5000)

```
