# Commands Windows 10
Useful commands and resources
## Remove data, unused space disk Windows 10
>cipher /W:e:\
## Set Read Only to USB ports
>Windows Registry Editor Version 5.00
>
>[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\StorageDevicePolicies]
>"WriteProtect"=dword:00000000

# Docker
## PostgreSQL
Backup de Base de Datos
>docker exec -t proy-postgres pg_dumpall -c -U postgres > "dump_$(Get-Date -format "yyyy-MM-dd-HHmm").sql"

Restore de Base de Datos
>cat dump_xxxxxx.sql | docker exec -i proy-postgres psql -U postgres
## Disk
Ubicacion de archivos en el disco
>C:\Users\<usuario>\AppData\Local\Docker\wsl\data
## Windows Volumes
Ubicacion de los Volumes
>\\wsl$\docker-desktop-data\version-pack-data\community\docker\volumes\
## IP Addres
Mostrar la direcciones IP de una instancia
>docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' cece0c5c952b
## shell
Ingresar al shell de un contenedor
>docker exec -it inspector_broker sh
## copy external
Copiar un archivo (inspector_broker.py) a un contenedor, en este caso 'inspector_broker' al directorio 'code'
>docker cp inspector_broker.py inspector_broker:/code/inspector_broker.py
