# Limitar la recursividad en Get-ChildItem con el parámetro -Depth
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2017/11/11/limitar-la-recursividad-en-get-childitem-con-el-parametro-depth/
```PowerShell
#Primer nivel
Get-ChildItem E:\powershell -Recurse -Depth 0
#Segundo nivel
Get-ChildItem E:\powershell -Recurse -Depth 1

```
