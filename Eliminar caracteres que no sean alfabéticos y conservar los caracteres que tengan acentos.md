# Eliminar caracteres que no sean alfabéticos y conservar los caracteres que tengan acentos
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2017/02/10/eliminar-caracteres-que-no-sean-alfabeticos-y-conservar-los-caracteres-que-tengan-acentos/
```PowerShell
$cadena = 'áéíóúabcdefg12345HIJKLMNOP!@#$%qrs)(*&^TUVWXyz'
$patron = '[^a-zA-Zá-úÁ-Ú]'
$cadena -replace $patron, ''

```
