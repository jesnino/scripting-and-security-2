# Ejecutar código PHP desde PowerShell
## PHP, PowerShell 
### URL: https://www.jesusninoc.com/2017/03/01/ejecutar-codigo-php-desde-powershell/
```PowerShell
cd C:\xampp\php

.\php.exe -r "echo 'Hola Mundo';"

'<?php echo ''Hola Mundo''; ?>' | .\php.exe
'<?php echo "Hola Mundo"; ?>' | .\php.exe
"<?php echo 'Hola Mundo'; ?>" | .\php.exe

```
