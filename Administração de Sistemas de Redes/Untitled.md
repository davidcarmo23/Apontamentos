HTTPS -> foi criado uma pasta para cada site de forma a fazer os ports 80  e 8080
DNS -> na pasta hosts tentou-se fazer o hierarquico e nao conseguimos
Firewall > Está feita , foram estabelecidas acess-lists para permitir apenas acesso interno
NTP -> Foi feito e dado o timezone 
NAS -> Configurado o servidor FreeNAS, demos um  ip para conseguir entrar na página de admin através de pcs, dentro do Nas criamos uma pool uma pasta de backups e uma de NFS, sharing foi o NFS apenas pode ser acedido internamente , foi editado o ficheiro fstab para dar mount do NAS no file explorer do pc no arranque 
Backup -> apenas o admin tem acesso, e foi criado utilizando um script bashrc com crontab para realizar os backups periódicos, calcula o dia , cria um backup local e depois copia os dados para o servidor NAS.

**Filesystems** 
NFS para Linux > Este foi utilizado -- 
Samba para Windows
AFP ([### Apple Filing Protocol](https://en.wikipedia.org/wiki/Apple_Filing_Protocol)) para Linux > 

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

- **LDAP**: São guardadas num serviço de diretoria do **OpenLDAP** e este serviço é de **natureza hierárquica** permitindo **organizar** as contas por **localização, função ou departamento** - **Potencial localização** dentro da rede de empresa.