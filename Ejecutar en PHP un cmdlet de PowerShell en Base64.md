# Ejecutar en PHP un cmdlet de PowerShell en Base64
## PHP, PowerShell 
### URL: https://www.jesusninoc.com/2018/02/21/ejecutar-en-php-un-cmdlet-de-powershell-en-base64/
```PowerShell
cd C:\xampp\php
 
"<?php system('powershell.exe -encodedcommand RwBlAHQALQBQAHIAbwBjAGUAcwBzAA=='); ?>" | .\php.exe

```
