# Añadir varios textos a un fichero y que queden en la misma línea
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2017/11/09/anadir-varios-textos-a-un-fichero-y-que-queden-en-la-misma-linea/
```PowerShell
"El texto tiene " | Out-File -FilePath fichero.txt -NoNewline
"que quedar en " | Add-Content -Path fichero.txt -NoNewline
"la misma línea." | Add-Content -Path fichero.txt -NoNewline

```
