# Enviar señales de radio desde Raspberry Pi mediante una conexión SSH desde PowerShell (parte 3)
## PowerShell, Radio 
### URL: https://www.jesusninoc.com/2018/02/24/enviar-senales-de-radio-desde-raspberry-pi-mediante-una-conexion-ssh-desde-powershell-parte-3/
```PowerShell
#Enviar mediante señales de radio el fichero que hemos subido
#Ejecutar fm_transmitter (use Raspberry Pi as FM transmitter)

#Iniciar una sesión SSH
#Para iniciar sesión SSH es necesario indicar la dirección IP del equipo al que nos vamos a conectar y también hay que introducir los credenciales (usuario y contraseña).

$sUser = "pi"
$Pass = ConvertTo-SecureString -String "raspberry" -AsPlainText -Force
$Credential = New-Object -TypeName "System.Management.Automation.PSCredential" -ArgumentList $sUser, $Pass
$oSessionSSH = New-SSHSession -ComputerName 192.168.1.161 -Force -Credential $Credential

#Crear canal de comunicación entre PowerShell y Linux (Raspberry Pi)
#Convertirse en sudo para ejecutar fm_transmitter

$stream = $oSessionSSH.Session.CreateShellStream("PS-SSH", 0, 0, 0, 0, 1000)
Invoke-SSHStreamExpectSecureAction -ShellStream $stream -Command "sudo su -" -ExpectString "[sudo] password for $($sUser):" -SecureAction $Pass

#Transmitir por radio en la frecuencia 90 MHz el saludo creado anteriormente
$stream.WriteLine("/home/pi/fmm/fm_transmitter-master/fm_transmitter -f 90 /home/pi/fmm/fm_transmitter-master/saludo.wav")

#Verificar que llega bien la señal desde SDR o desde una radio FM en la frecuencia 90 MHz

```
