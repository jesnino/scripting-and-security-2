# Listar los atributos de los ficheros que se encuentran en carpetas compartidas
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2018/05/25/listar-los-atributos-de-los-ficheros-que-se-encuentran-en-carpetas-compartidas/
```PowerShell
(Get-SmbShare).Path | ls -Force | gi -Force | select FullName, @{n="Attr";e={[string]$_.attributes}}

```
