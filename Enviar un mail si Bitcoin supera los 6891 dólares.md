# Enviar un mail si Bitcoin supera los 6891 dólares
## Cryptography, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/19/enviar-un-mail-si-bitcoin-supera-los-6891-dolares/
```PowerShell
$url="https://www.plus500.es/Instruments/BTCUSD"
$result = Invoke-WebRequest $url
$valor = $result.AllElements | Where Class -eq “inst-rate” | %{$_.innerText}
if ([Int]$valor -gt 6891)
{
    "Supera los 6891"
    $componer = "Supera los 6891"
    Send-MailMessage -to "mail2@example.com" -from “mail@example.com” -subject "Bitcoin supera los 6891" -SmtpServer localhost -Body $componer
}

```
