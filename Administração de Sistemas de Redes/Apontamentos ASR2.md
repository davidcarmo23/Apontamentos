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

Num sistema 