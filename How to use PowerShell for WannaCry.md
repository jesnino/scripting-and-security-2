# How to use PowerShell for WannaCry
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/05/17/how-to-use-powershell-for-wannacry/
```PowerShell
#How to use PowerShell to check if a hotfix is installed
Get-HotFix | Select-Object hotfixid | Select-String "KB4013429"

#PowerShell Port Checking
Test-NetConnection -ComputerName 127.0.0.1 -Port 445

#Testing if a domain resolves with PowerShell
Resolve-DnsName www.iuqerfsodp9ifjaposdfjhgosurijfaewrwergwea.com

#How to disable SMBv1 with PowerShell
#On Windows 8 and Windows Server 2012
Set-SmbServerConfiguration -EnableSMB1Protocol $false

```
