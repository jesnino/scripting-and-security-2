# Detectar las palabras que están mal escritas en una noticia de un diario con un comando en Linux y ejecutarlo con WSL (Windows Subsystem for Linux) desde PowerShell
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/17/detectar-las-palabras-que-estan-mal-escritas-en-un-articulo-de-un-diario-con-un-comando-en-linux-y-ejecutarlo-con-wsl-windows-subsystem-for-linux-desde-powershell/
```PowerShell
$url="https://www.elconfidencial.com/espana/comunidad-valenciana/2018-06-17/aquarius-tarifa-pateras-inmigrantes-solidaria-espana_1580012/"
$result = Invoke-WebRequest $url
$texto = $result.AllElements | Where Class -eq “news-body-center cms-format ” | %{$_.innerText}
$texto | bash -c 'aspell list --encoding iso-8859-1 -d es' | Group-Object | Select-Object Name

```
