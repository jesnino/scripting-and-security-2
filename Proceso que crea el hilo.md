# Proceso que crea el hilo
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2018/05/12/proceso-que-crea-el-hilo/
```PowerShell
(Get-WmiObject -Class Win32_Thread) | %{
    $_.Handle, (Get-Process -Id $_.ProcessHandle).ProcessName
}

```
