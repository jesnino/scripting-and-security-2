# Buscar archivos png en una web con WSL (Windows Subsystem for Linux) desde PowerShell
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/13/buscar-archivos-png-en-una-web-con-wsl-windows-subsystem-for-linux-desde-powershell/
```PowerShell
bash -c "wget -r -l3 -t1 -nd -N -np -A.png -erobots=off https://www.jesusninoc.com"

```
