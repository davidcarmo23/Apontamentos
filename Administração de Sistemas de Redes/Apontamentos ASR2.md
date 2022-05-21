# Aula 7
## Executar trabalhos a tempos regulares
**Crontab** -> Utilizado para permitir a um anfitrião executar comandos a tempos regulares 
O utilizador cria um ficheiro crontab que executa os comandos dentro de si dentro das configurações que lhe foram passadas.

**É um editor do tipo vi**

## Gestão de utilizadores
Management de utilizadores é tudo sobre fazer interfacing de humanos para computadores , isto traz a luz problemas como:
- Accounting -> registar novos utilizadores e apagar antigos
- Conforto e conveniência
- Serviços de suporte
- Problemas éticos
- Manutenção de confiança e segurança

Alguns destes são **problemas tecnológicos** outros são **problemas humanos**
**Conforto e conveniência** encontra-se no meio
Manutenção de utilizadores é importante pois o sistema existe para ser utilizado por seres  humanos, e são tanto amigo como inimigo

É **diferente** criar um utilizador local (para uma máquina) ou um utilizador para uma comunidade de máquinas

Cada OS tem uma forma específica de criação de um utilizador local (alguns têm ferramentas gráficas) coisas a ter em conta:

- nome do utilizador (ter um modelo)
- password inicial (ter um modelo)
- grupos a que pertence (ter um modelo)
- acesso a recursos locais (ter um modelo)

## Trabalhar com Utilizadores e Grupos
- Gerir utilizadores e grupos
	- Contas de utilizador Linux
	- Grupos Linux
- Gerir ownership, permissões e quotas

## Como funcionam Contas de Utilizador Linux
- Utilizador
- Password

Por default todos as diretorias home de todos os utilizadores são criados e mantidos na diretoria **/home**.
A diretoria home do utilizador root é **/root**

Para ver toda a informação sobre o **user** no sistema Linux 
- finger **user**
	- A informação seguinte seria apresentada :
		- **Login** -> utilizador que está a ser utilizado para autenticar ao sistema
		-  **Name** -> Nome completo do **user**
		- **Directory** -> Diretoria Home do **user**
		- **Shell** -> Shell default que vai ser providenciada ao **user**
		- **Last Login** -> Mostra a última vez que o **user** fez login e donde
Para além desta informação cada conta de utilizador é atribuida um **unique user ID (UID)**. Nunca existem 2 contas com o mesmo UID
Para ver este UID basta utilizar o comando
**id username**

Num sistema de SUSE Linux o primeiro user regular é dado o UID de **1000** e os seguintes serão dados apartir desse. Fedora começa no **500**

A conta de utilizador de **root** é sempre dado o **UID 0**. É este UID que o OS utiliza para controlar o acesso aos ficheiros e diretorias no file system

## Onde o Linux guarda as suas contas de utilizador
Ao instalarmos o OS somos dados a escolher várias opções donde vamos querer guardar as nossas contas de utilizador.

São nos dados os seguintes métodos de autenticação para escolher:
- **Local** -> As contas são **guardadas** no ficheiro /etc/psswd
- **LDAP** -> São guardadas num serviço de diretoria do **OpenLDAP** e este serviço é de **natureza hierárquica** permitindo **organizar** as contas por **localização, função ou departamento**
- **NIS** -> Network Information Service é desenhado para providenciar gestão de contas de utilizador centralizadamente quando temos vários sistemas que têm de ter as mesmas contas. O NIS configura os sistemas para utilizarem um ficheiro passwd e shadow comum
- **Windows Domain** -> Se tivermos um controlador de dominio windows na nossa rede podemos configurar o nosso sistema Linux para utilizar as contas de utilizador no dominio para autenticar o sistema local

## **Opções Locais**
- **/etc/passwd** -> This file contains the user account information for your system.
- **/etc/shadow** -> This file contains passwords for your user accounts.
- **/etc/group** -> This file contains your system’s groups.


### /etc/passwd File
->Username:Password:UID:GID:Full_Name:Home_Directory:Default_Shell■Username:The Username field simply identifiesthe username the user will supply when logging into the system■Password:This is a legacy field. At one time, theuser’s password was stored in encrypted form inthis field in the passwd file. However, for securityreasons, the password has been moved from/etc/passwdto/etc/shadow.
    
2.  ![aula ASR 7 21-22.pdf](https://uc1f19c645b6aa4468aca9db3dda.previews.dropboxusercontent.com/p/pdf_img/ABj0dBnV60-bxTzfwQ6yi38sgigiueD4IQh5Y0A_qZpwcJ-P6zk6mflZmTippBI13ffrZs3QTHrZihphH5mKzYl9huR-frAWqdMu-Bljr7FOOEpyVHfE-CWV9fBxzUUHT2OFiaBwI1aXhPizabi8MChfb25vRvDm3xF7PC6GhNfhrfaERgwfYFKJWm7FVFW8JJlaKEtPFgn81wnphorIALQe1C6Wg1XhmNHbt6mzlyWbGs4cdh7w53FrYMrVoUy0nN7Cq-Qr5RdAFs-QxWdgDGVd78cSbZECDKJbbFOTHx9JQnKoJ8_J6bddypbHNhn2YJSF4uMEG6Mj5zWKSN5ddiqJ0yaBrlbImtLmehme--vknJHv3BPMML9JqjdkfNzP7xmAJ6vp7cM0bXBnxliPmg9O/p.png?page=25&scale_percent=0)
    
    ■UIDThis is the user ID for the user account■GIDThis field references the group ID numberof the user’s default group■Full_NameThis field contains the user’s fullname■Home_DirectoryThis field contains the path tothe user’s home directory.■Default_ShellThis field specifies the shell thatwill be used by default
