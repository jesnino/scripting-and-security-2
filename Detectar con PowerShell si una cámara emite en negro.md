# Detectar con PowerShell si una cámara emite en negro
## PowerShell 
### URL: https://www.jesusninoc.com/2018/02/24/detectar-con-powershell-si-una-camara-emite-en-negro/
```PowerShell
# Código de estado

if ((Invoke-WebRequest "https://i0.wp.com/www.jesusninoc.com/wp-content/uploads/2018/02/910.jpg?ssl=1" ).StatusCode -ne 200)
{
    "Error de código de estado"
}
else
{
    "Sin error de código de estado"
}

# Tamaño de la imagen en bytes

if ((Invoke-WebRequest "https://i0.wp.com/www.jesusninoc.com/wp-content/uploads/2018/02/910.jpg?ssl=1").RawContentLength -ne 7500)
{
    "Tamaño de la imagen inferior a lo normal"
}
else
{
    "Tamaño de la imagen normal"
}

# Color que predomina en la imagen (si el color que predomina es el negro, habrá que comprobar la imagen)

if (((Invoke-WebRequest "https://i0.wp.com/www.jesusninoc.com/wp-content/uploads/2018/02/910.jpg?ssl=1").content | Group-Object | Sort-Object count | Select-Object -Last 1).name -eq 0)
{
    "El color negro predomina en la imagen"
}
else
{
    "Imagen con colores normales"
}

```
