# Retos en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2016/01/01/retos-en-powershell/
```PowerShell
"notepad" > fichero.txt; saps(gc (ls ./fichero.txt))

```
```PowerShell
(ps).Name

```
```PowerShell
1..100

```
```PowerShell
1..6 | %{Get-Random (1..50)}

```
```PowerShell
mkdir (1..100)

```
```PowerShell
#Con WhatIf simula la creación de las carpetas
$ruta="";1..10 | %{$ruta=$ruta+[String]$_+"\"}
mkdir $ruta -WhatIf

```
```PowerShell
1..100 | %{$_}

```
```PowerShell
ni (Get-Date).tostring("dd-MM-yyyy-hh-mm-ss") -Value ([String](ps).Name)

```
```PowerShell
1..100 | %{New-LocalUser $_}

```
```PowerShell
(Get-LocalUser).name | %{Remove-LocalUser $_ -WhatIf}

```
```PowerShell
ls -Recurse | Select-String "hola"

```
```PowerShell
#Error al ejecutar el programa ping
ping 192.168.11111.11111;$LASTEXITCODE;$?
#No error al ejecutar el programa ping
ping 192.168.1.1;$LASTEXITCODE;$?

```
```PowerShell
(Get-Date).AddDays(-(Get-Random (1..(5*365))))

```
