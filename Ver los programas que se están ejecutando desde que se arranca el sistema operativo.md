# Ver los programas que se están ejecutando desde que se arranca el sistema operativo
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2017/11/26/ver-los-programas-que-se-estan-ejecutando-desde-que-se-arranca-el-sistema-operativo/
```PowerShell
Get-WmiObject win32_process | Sort-Object Processid | Select-Object Processid,Name,CommandLine

```
