# Physically labeled bank where the memory is located
## Memory, PowerShell 
### URL: https://www.jesusninoc.com/2017/09/03/physically-labeled-bank-where-the-memory-is-located/
```PowerShell
Get-WmiObject Win32_PhysicalMemory | Select-Object BankLabel

```
