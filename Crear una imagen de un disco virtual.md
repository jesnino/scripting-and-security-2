# Crear una imagen de un disco virtual
## PowerShell, Virtualization 
### URL: https://www.jesusninoc.com/2017/10/25/crear-una-imagen-de-un-disco-virtual/
```PowerShell
#Crear disco virtual en la unidad d
New-VHD –Path d:\disc.vhdx –SizeBytes 1GB
#Montar el disco virtual creado
Mount-VHD –Path d:\disc.vhdx
#Crear imagen de la unidad montada anteriormente (por ejemplo unidad e) y almacenarla en d
New-WindowsImage -ImagePath "d:\imagen.wim" -CapturePath "e:\" -Name "Unidad e"

```
