# Enviar un mail de felicitación de cumpleaños con PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/04/12/enviar-un-mail-de-felicitacion-de-cumpleanos-con-powershell/
```PowerShell
$csv = @'  
fecha,nombre,correo
07/04/2018,Juan,juan@example.com,
14/04/2018,Marta,marta@example.com,
'@ 
 
$data = $csv | ConvertFrom-Csv

$data | %{
    # Enviar mail cuando sea el día del cumpleaños
    if ((Get-Date  -Format d) -eq ($_.fecha)){
        $componer = "Te deseo un feliz cumpleaños " + $_.nombre
        Send-MailMessage -to $_.correo -from “mail@example.com” -subject "Feliz cumpleaños" -SmtpServer localhost -Body $componer
    }
}

```
