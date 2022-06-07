**Filesystems** 
NFS para Linux > Este foi utilizado -- 
Samba para Windows
AFP([### Apple Filing Protocol](https://en.wikipedia.org/wiki/Apple_Filing_Protocol)) para Linux > 

Poderia ser FTP em vez do **FreeNAS** (problemas de segurança no FTP)
NAS -> Network Attached Storage 

![[Pasted image 20220607095820.png]]
![[Pasted image 20220607100443.png]]

**Desastres**
Não existe redundância na ligação com o R1(**Minimização** é redundância e **mitigação** é reparação) e também de dados(Não existir o RAID)
Não existe também redundância de servidores, se for perdido ao o acesso ao NAS perde-se o acesso à cópias de segurança.

**Problemas de malware** -> Minimização (boas práticas, antivirus e consultar fóruns) Mitigação (Antivirus e serviços atualizados)
**Roubo** ->
**Single point Failures** - > Routers e switches (**Minimizar** eliminar o SPF, **mitigação** reparação de serviço, uso de backup e substituição )
![[Pasted image 20220607100211.png]]
**Logs** de firewalls, acesso indevido(exterior), de utilizadores, dos backups e acesso aos mesmos, de acesso ao site