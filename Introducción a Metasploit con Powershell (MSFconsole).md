# Introducción a Metasploit con Powershell (MSFconsole)
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2017/01/01/introduccion-a-metasploit-con-powershell-msfconsole/
```PowerShell
#Realizado por Julián Martínez

#The msfconsole is probably the most popular interface to the Metasploit Framework (MSF). It provides an “all-in-one” centralized console and allows you efficient access to virtually all of the options available in the MSF. MSFconsole may seem intimidating at first, but once you learn the syntax of the commands you will learn to appreciate the power of utilizing this interface.

#Listar opciones para usar msfconsole
msfconsole -h

#Listar comandos que podemos utilizar en Metasploit
msfconsole -x help -x exit

#Desplegar lista de exploits
msfconsole -x show exploits -x exit

#Desplegar lista de payloads
msfconsole -x show payloads -x exit

```
