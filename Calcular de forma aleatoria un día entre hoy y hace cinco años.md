# Calcular de forma aleatoria un día entre hoy y hace cinco años
## PowerShell 
### URL: https://www.jesusninoc.com/2017/08/15/calcular-de-forma-aleatoria-un-dia-entre-hoy-y-hace-cinco-anos/
```PowerShell
#Día aleatorio entre hoy y hace cinco años
$diaaleatorio=Get-Random (1..(5*365))
(Get-Date).AddDays(-$diaaleatorio)

```
