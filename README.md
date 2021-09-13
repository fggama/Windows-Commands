# Commands
Useful commands and resources
## Remove data, unused space disk Windows 10
>cipher /W:e:\
## Set Read Only to USB ports
>Windows Registry Editor Version 5.00
>
>[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\StorageDevicePolicies]
>"WriteProtect"=dword:00000000

# Docker
## Backup PostgreSQL, Docker
>docker exec -t proy-postgres pg_dumpall -c -U postgres > "dump_$(Get-Date -format "yyyy-MM-dd-HHmm").sql"
## Restore PostgreSQL
>cat dump_xxxxxx.sql | docker exec -i proy-postgres psql -U postgres
## Disk: 
>C:\Users\garciafr\AppData\Local\Docker\wsl\data
## Volumes en Windows: 
>\\wsl$\docker-desktop-data\version-pack-data\community\docker\volumes\