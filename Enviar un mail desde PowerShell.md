# Enviar un mail desde PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/11/enviar-un-mail-desde-powershell/
```PowerShell
$componer = "Contenido de prueba"
Send-MailMessage -to "mail2@example.com" -from “mail@example.com” -subject "Correo de prueba" -SmtpServer localhost -Body $componer

```
