# Descargar las imágenes de una página web con curl mediante WSL desde PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2018/05/29/descargar-las-imagenes-de-una-pagina-web-con-curl-mediante-wsl-desde-powershell/
```PowerShell
wsl wget -nd -H -p -A jpg,jpeg,png,gif -e robots=off https://www.jesusninoc.com/2018/05/13/get-rss-feed-from-jesusninoc-com-new-version/

```
