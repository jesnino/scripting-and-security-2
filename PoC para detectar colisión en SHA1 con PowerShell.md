# PoC para detectar colisión en SHA1 con PowerShell
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/02/24/poc-para-detectar-colision-en-sha1-con-powershell/
```PowerShell
#Más información: https://shattered.io/
#https://isc.sans.edu/forums/diary/Practical+collision+attack+against+SHA1/22109/
Start-BitsTransfer "https://shattered.io/static/shattered-1.pdf"
Start-BitsTransfer "https://shattered.io/static/shattered-2.pdf"
Get-FileHash .\shattered-1.pdf -Algorithm SHA1
Get-FileHash .\shattered-2.pdf -Algorithm SHA1

```
