# Crear una base de datos en MySQL con PowerShell
## Database, PowerShell 
### URL: https://www.jesusninoc.com/2017/01/11/crear-una-base-de-datos-en-mysql-con-powershell/
```PowerShell
[void][System.Reflection.Assembly]::LoadWithPartialName("MySql.Data")
$Connection = New-Object MySql.Data.MySqlClient.MySqlConnection
$ConnectionString = "server=" + "localhost" + ";port=3306;uid=" + "root" + ";pwd=" + ";"
$Connection.ConnectionString = $ConnectionString
$Connection.Open()

$Query = 'CREATE database Users'
$Command = New-Object MySql.Data.MySqlClient.MySqlCommand($Query, $Connection)
$DataAdapter = New-Object MySql.Data.MySqlClient.MySqlDataAdapter($Command)
$DataSet = New-Object System.Data.DataSet
$RecordCount = $dataAdapter.Fill($dataSet, "data")
$DataSet.Tables[0]
$Connection.Close()

```
