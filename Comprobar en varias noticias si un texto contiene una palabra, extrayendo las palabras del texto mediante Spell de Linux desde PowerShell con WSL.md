# Comprobar en varias noticias si un texto contiene una palabra, extrayendo las palabras del texto mediante Spell de Linux desde PowerShell con WSL
## Bash, PowerShell 
### URL: https://www.jesusninoc.com/2018/06/30/comprobar-en-varias-noticias-si-un-texto-contiene-una-palabra-extrayendo-las-palabras-del-texto-mediante-spell-de-linux-desde-powershell-con-wsl/
```PowerShell
# Descargar el fichero RSS
$web = (Invoke-WebRequest "https://rss.elconfidencial.com/espana/").content

# Convertir para ver las palabras con acentos
$utf8 = [System.Text.Encoding]::GetEncoding(65001)
$iso88591 = [System.Text.Encoding]::GetEncoding(28591) #ISO 8859-1 ,Latin-1
$wrong_bytes = $utf8.GetBytes($web)
$right_bytes = [System.Text.Encoding]::Convert($utf8,$iso88591,$wrong_bytes)
$right_string = $utf8.GetString($right_bytes)

# Detectar las palabras que están mal escritas en cada artículo
# https://www.jesusninoc.com/2018/06/17/detectar-las-palabras-que-estan-mal-escritas-en-un-articulo-de-un-diario-con-un-comando-en-linux-y-ejecutarlo-con-wsl-windows-subsystem-for-linux-desde-powershell/
$xml = [xml]$right_string
$xml.feed.entry | %{
    $_.id
    # Spell http://www.linfo.org/spell.html
    $_.content.'#cdata-section' -replace "<.*?>" | bash -c 'spell' | Group-Object | Where-Object {$_.Name -match "Sánchez"}
}

```
