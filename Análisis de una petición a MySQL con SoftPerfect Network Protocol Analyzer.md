# Análisis de una petición a MySQL con SoftPerfect Network Protocol Analyzer
## Database, Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/03/31/analisis-de-una-peticion-a-mysql-con-softperfect-network-protocol-analyzer/
```PowerShell
[void][System.Reflection.Assembly]::LoadWithPartialName("MySql.Data")
$Connection = New-Object MySql.Data.MySqlClient.MySqlConnection
$ConnectionString = "server=" + "192.168.1.104" + ";port=3306;uid=" + "prueba" + ";pwd=pass" + ";database="+"estado"
$Connection.ConnectionString = $ConnectionString
$Connection.Open()

$Query='select PersonID,Estado from Persons'
$Command = New-Object MySql.Data.MySqlClient.MySqlCommand($Query, $Connection)
$DataAdapter = New-Object MySql.Data.MySqlClient.MySqlDataAdapter($Command)
$DataSet = New-Object System.Data.DataSet
$RecordCount = $dataAdapter.Fill($dataSet, "data")
$DataSet.Tables[0]
$Connection.Close()

```
