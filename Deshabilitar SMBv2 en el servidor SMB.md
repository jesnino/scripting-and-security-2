# Deshabilitar SMBv2 en el servidor SMB
## Filesystem, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/06/06/deshabilitar-smbv2-en-el-servidor-smb/
```PowerShell
Set-SmbServerConfiguration -EnableSMB2Protocol $false

```
