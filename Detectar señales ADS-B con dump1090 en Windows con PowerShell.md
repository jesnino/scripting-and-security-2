# Detectar señales ADS-B con dump1090 en Windows con PowerShell
## PowerShell, Radio 
### URL: https://www.jesusninoc.com/2017/10/22/detectar-senales-ads-b-con-dump1090-en-windows-con-powershell/
```PowerShell
Start-Process -File .\dump1090.bat -RedirectStandardOutput resultado.txt
Start-Sleep -Seconds 30
Stop-Process -Name cmd
Stop-Process -Name dump1090
Get-Content resultado.txt | Out-File procesado.txt -Append
rm resultado.txt

Start-Sleep -Seconds 5
(Get-Content .\procesado.txt) -split "`n" | %{
$_ | Select-String " S " | Out-File fin.txt -Append
}

$fly=Import-Csv -Encoding Unicode .\fin.txt
rm .\soluc.txt
"Hex     ,Mode  ,Sqwk  ,Flight   ,Alt    ,Spd  ,Hdg    ,Lat      ,Long   ,Sig  ,Msgs   ,Ti" | out-file soluc.txt
$fly.H1 -split "`n" | %{($_).Substring(0,8)+","+($_).Substring(8,6)+","+($_).Substring(14,6)+","+($_).Substring(20,9)+","+($_).Substring(29,7)+","+($_).Substring(36,5)+","+($_).Substring(41,6)+","+($_).Substring(47,9)+","+($_).Substring(56,9)+","+($_).Substring(65,6)+","+($_).Substring(71,6)+","+($_).Substring(77,1) | Out-File soluc.txt -append}

$flyfinal=Import-Csv -Encoding Unicode .\soluc.txt
$flyfinal.'Flight ' | Group-Object
$flyfinal.'Flight ' | Group-Object | Select name | Select-String "VLG81EF"
$flyfinal.'Flight ' | Group-Object | Select name | Select-String "VLG81E2"

```
