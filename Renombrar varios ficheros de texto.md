# Renombrar varios ficheros de texto
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/11/renombrar-varios-ficheros-de-texto/
```PowerShell
Get-ChildItem *.txt | %{
    Rename-Item -Path $_ -NewName "$($_.basename).bak" -WhatIf
}

```
