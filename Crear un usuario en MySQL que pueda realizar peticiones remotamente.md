# Crear un usuario en MySQL que pueda realizar peticiones remotamente
## Database 
### URL: https://www.jesusninoc.com/2017/03/30/crear-un-usuario-en-mysql-que-pueda-realizar-peticiones-remotamente/
```PowerShell
mysql -u root
CREATE USER 'prueba'@'localhost' IDENTIFIED BY 'pass';
GRANT ALL PRIVILEGES ON *.* TO 'prueba'@'localhost' WITH GRANT OPTION;
CREATE USER 'prueba'@'%' IDENTIFIED BY 'pass';
GRANT ALL PRIVILEGES ON *.* TO 'prueba'@'%'WITH GRANT OPTION;

```
