# Descargar un script en Bash almacenado en Github y ejecutarlo con WSL (Windows Subsystem for Linux) desde PowerShell
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/12/descargar-un-script-en-bash-almacenado-en-github-y-ejecutarlo-con-wsl-windows-subsystem-for-linux-desde-powershell/
```PowerShell
bash -c "wget https://raw.githubusercontent.com/jesusninoc/Bash/master/Repaso/UtilizarCadenas.sh"
gc .\UtilizarCadenas.sh | %{
    $_
    bash -c "$_"
    Start-Sleep -Seconds 5
}

```
