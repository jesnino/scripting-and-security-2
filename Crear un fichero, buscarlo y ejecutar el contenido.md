# Crear un fichero, buscarlo y ejecutar el contenido
## PowerShell 
### URL: https://www.jesusninoc.com/2016/11/22/crear-un-fichero-buscarlo-y-ejecutar-el-contenido/
```PowerShell
"notepad" > fichero.txt; Start-Process(Get-Content (Get-ChildItem ./fichero.txt))
"notepad" > fichero.txt; saps(gc (ls ./fichero.txt))

```
