# Changes the network category of a connection profile
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/10/10/changes-the-network-category-of-a-connection-profile/
```PowerShell
$a=Get-NetConnectionProfile -InterfaceIndex 11
$a.NetworkCategory = "Private"
Set-NetConnectionProfile -InputObject $a

```
