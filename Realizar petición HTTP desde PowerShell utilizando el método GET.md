# Realizar petición HTTP desde PowerShell utilizando el método GET
## PHP, PowerShell 
### URL: https://www.jesusninoc.com/2018/03/31/realizar-peticion-http-desde-powershell-utilizando-el-metodo-get/
```PowerShell
cd C:\xampp\php

'<?php echo htmlspecialchars($_GET[''nombre'']) . " tiene " . (int)$_GET[''edad''] . " años." ?>'| out-file scriptphp.php -Encoding utf8

.\php-cgi.exe -f .\scriptphp.php nombre=Marta edad=20

```
