# Almacenar la información enviada entre un cliente y un servidor en una base de datos MySQL con PowerShell
## Database, Network, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/15/almacenar-la-informacion-enviada-entre-un-cliente-y-un-servidor-en-una-base-de-datos-mysql-con-powershell/
```PowerShell
##Server
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
$valoresalmacenar=[Text.Encoding]::ASCII.GetString($content)

[void][System.Reflection.Assembly]::LoadWithPartialName("MySql.Data")
$Connection = New-Object MySql.Data.MySqlClient.MySqlConnection
$ConnectionString = "server=" + "localhost" + ";port=3306;uid=" + "root" + ";pwd=" + ";database="+"estado"
$Connection.ConnectionString = $ConnectionString
$Connection.Open()

$Query = 'INSERT INTO Persons (PersonID,LastName,FirstName,Address,City,Estado) VALUES ('+$valoresalmacenar+')'
$Query
$Command = New-Object MySql.Data.MySqlClient.MySqlCommand($Query, $Connection)
$DataAdapter = New-Object MySql.Data.MySqlClient.MySqlDataAdapter($Command)
$DataSet = New-Object System.Data.DataSet
$RecordCount = $dataAdapter.Fill($dataSet, "data")
$DataSet.Tables[0]
$Connection.Close()

$udpclient.Close()

```
```PowerShell
##Client
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$b=[Text.Encoding]::ASCII.GetBytes('"2","Grillo","Pepito","Castellana","Berlin","1"')
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
```PowerShell
[void][System.Reflection.Assembly]::LoadWithPartialName("MySql.Data")
$Connection = New-Object MySql.Data.MySqlClient.MySqlConnection
$ConnectionString = "server=" + "localhost" + ";port=3306;uid=" + "root" + ";pwd=" + ";database="+"estado"
$Connection.ConnectionString = $ConnectionString
$Connection.Open()

$Query='select PersonID,FirstName,Estado from Persons'
$Command = New-Object MySql.Data.MySqlClient.MySqlCommand($Query, $Connection)
$DataAdapter = New-Object MySql.Data.MySqlClient.MySqlDataAdapter($Command)
$DataSet = New-Object System.Data.DataSet
$RecordCount = $dataAdapter.Fill($dataSet, "data")
$DataSet.Tables[0]
$Connection.Close()

```
