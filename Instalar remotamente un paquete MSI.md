# Instalar remotamente un paquete MSI
## PowerShell, Software 
### URL: https://www.jesusninoc.com/2017/05/27/instalar-remotamente-un-paquete-msi/
```PowerShell
$Equipo = 'equipo1'
$RutaMSI = '\\servidor\paquete.msi'
 
$WMIclass = [wmiclass]"\\$Equipo\ROOT\cimv2:Win32_Product"
$WMIclass.Install($RutaMSI)

```
