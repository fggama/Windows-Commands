# Commands Windows 10
Comandos utiles

## Borrar datos de espacio en disco sin utilizar
>``cipher /W:e:\``

## Environment variables
``CMD: echo %path%``

Accede al entorno  
``PS: Set-Location Env:``

Lista variables de entorno  
``PS Env:\> ls``  
``PS Env:\> Get-ChildItem``

Imprime el valor de _path_  
``$Env:path``


## Read Only USB ports
Windows Registry Editor Version 5.00

>[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\StorageDevicePolicies]  
>"WriteProtect"=dword:00000000

## Conexión remota con **SysinternalsSuite**  
``psexec \\NOMBREPC cmd``  

## Obtener información detallada de la PC  
``systeminfo /fo (list | table | csv)``  
``wmic computersystem get Name,domain,Manufacturer,Model,NumberofProcessors,PrimaryOwnerName,Username,Roles,totalphysicalmemory /format:list``  

## NIC  
Info de las tarjetas de red y protocolos  
``wmic nicconfig get caption,index,TcpipNetbiosOptions``  
````
wmic nicconfig get MACAddress,IPAddress,DNSHostName,DNSDomain,DNSDomainSuffixSearchOrder,DNSEnabledForWINSResolution,DNSServerSearchOrder /format:list
````  
``wmic nic get AdapterType,AutoSense,Name,Installed,MACAddress,PowerManagementSupported,Speed,StatusInfo``  
``wmic netprotocol get Caption,Description,GuaranteesSequencing,SupportsBroadcasting,SupportsEncryption,Status /format:list``  

## Printers
>- wmic  
>``wmic:root\cli>/node:NOMBREPC printer list status``   

Lista de impresoras  
``wmic printer list brief``  

[Ver mas de WMIC](https://learn.microsoft.com/en-us/windows/win32/wmisdk/wmic)  

>Desinstalar impresora remota  
>````RUNDLL32 printui.dll,PrintUIEntry /n "HP Color LaserJet Pro MFP M477 RANF" /dl````  

## Servicios
Ver servicios activos  
``net start``  
Ver **todos** los servicios  
``sc queryex type=service state=all``  
