# Liberar memoria en PowerShell mediante el Garbage Collector de .NET
## Memory, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/13/liberar-memoria-en-powershell-mediante-el-garbage-collector-de-net/
```PowerShell
[System.GC]::Collect()
[GC]::Collect()

```
