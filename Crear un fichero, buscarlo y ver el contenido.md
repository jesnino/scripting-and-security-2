# Crear un fichero, buscarlo y ver el contenido
## PowerShell 
### URL: https://www.jesusninoc.com/2016/11/20/crear-un-fichero-buscarlo-y-ver-el-contenido/
```PowerShell
"hola" > fichero.txt; Get-Content (Get-ChildItem ./fichero.txt)
"hola" > fichero.txt; gc (ls ./fichero.txt)

```
