# ASR FREQ 2 - Maninhos

# Aula 7

Crontab - automação de sistemas de administração

## Executar trabalhos a tempos regulares
**Crontab** -> Utilizado para permitir a um anfitrião executar comandos em tempos regulares 
O utilizador cria um ficheiro crontab que executa os comandos dentro de si, dentro das configurações que lhe foram passadas.

**É um editor do tipo vi**

## Gestão de utilizadores
Management de utilizadores é tudo sobre fazer interfacing de humanos para computadores , isto traz a luz problemas como:
- Accounting -> registar novos utilizadores e apagar antigos
- Conforto e conveniência
- Serviços de suporte
- Problemas éticos
- Manutenção de confiança e segurança

Alguns destes são **problemas tecnológicos** outros são **problemas humanos**,
**Conforto e conveniência** encontra-se no meio.
Manutenção de utilizadores é importante,pois o sistema existe para ser utilizado por seres  humanos, que podem ser amigos ou inimigos.

É **diferente** criar um utilizador local (para uma máquina) ou um utilizador para uma comunidade de máquinas.

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

Por defeito todas as diretorias home, de todos os utilizadores são criados e mantidos na diretoria **/home**.
A diretoria home do utilizador root é **/root**

Para ver toda a informação sobre o **user** no sistema Linux 
- finger **user**
	- A informação seguinte seria apresentada :
		- **Login** -> utilizador que está a ser utilizado para autenticar ao sistema
		-  **Name** -> Nome completo do **user**
		- **Directory** -> Diretoria Home do **user**
		- **Shell** -> Shell default que vai ser providenciada ao **user**
		- **Last Login** -> Mostra a última vez que o **user** fez login e donde para além desta informação cada conta de utilizador é atribuida um **unique user ID (UID)**. Nunca existem 2 contas com o mesmo UID. Para ver este UID basta utilizar o comando **id username**.

Num sistema de SUSE Linux o primeiro user regular é dado o UID de **1000** e os seguintes serão dados apartir desse. Fedora começa no **500**.

A conta de utilizador de **root** é sempre dado o **UID 0**. É este UID que o OS utiliza para controlar o acesso aos ficheiros e diretorias no file system.

## Onde o Linux guarda as suas contas de utilizador
Ao instalarmos o OS somos dados a escolher várias opções donde vamos querer guardar as nossas contas de utilizador.

São nos dados os seguintes métodos de autenticação para escolher:
- **Local**: As contas são **guardadas** no ficheiro **/etc/psswd**
- **LDAP**: São guardadas num serviço de diretoria do **OpenLDAP** e este serviço é de **natureza hierárquica** permitindo **organizar** as contas por **localização, função ou departamento**
- **NIS**: Network Information Service é desenhado para providenciar gestão de contas de utilizador centralizadamente quando temos vários sistemas que têm de ter as mesmas contas. O NIS configura os sistemas para utilizarem um ficheiro passwd e shadow comum
- **Windows Domain**: Se tivermos um controlador de dominio windows na nossa rede podemos configurar o nosso sistema Linux para utilizar as contas de utilizador no dominio para autenticar o sistema local

## **Opções Locais**
- **/etc/passwd**: Este ficheiro contém as informações da conta do utilizador para o sistema
- **/etc/shadow**: Este ficheiro contém as passwords para as contas de utilizador
- **/etc/group**: Este ficheiro contém os grupos do sistema


### /etc/passwd File
- Conteúdo ->Username:Password:UID:GID:Full_Name:Home_Directory:Default_Shell
![](https://i.imgur.com/BNWrHBS.png)
![](https://i.imgur.com/PUxULFV.png)

### /etc/passwd File
- Conteúdo ->Username:Password:Last_Modified:Min_Days:Max_Days:Days_Warn:Disabled_Days:Expire
![](https://i.imgur.com/m1r90xT.png)
![](https://i.imgur.com/Yp9Ptbr.png)
![](https://i.imgur.com/XLknaUc.png)

**Para verificar estes dois ficheiros basta utilizar o comando pwck, caso os ficheiros estejam desincronizados pode-se utilizar pwconv para compor os ficheiros** -> Este vai adicionar contas de utilizador que faltem a ambos os ficheiros

## Criar e Gerir Contas de Utilizador pela linha de comandos

### useradd
**Syntax** -> useradd options username
**Opções default** -> A conta criada com useradd ncth ncth utiliza os parametros default contidos no ficheiro de configuração **/etc/default/useradd**
**/etc/login.defs** -> Contém valores  que podem ser utilizados para os parametros de GID e UID quando criada uma conta com o commando useradd, também contém os defaults para criar passwords em /etc/shadow -> conseguimos ver os valores default com **useradd -D**

#### Options 
![](https://i.imgur.com/IfsjZhA.png)
![](https://i.imgur.com/KXvBlnm.png)
![](https://i.imgur.com/89WpYvG.png)


### passwd
**Este comando é utilizado para mudar a palavra passe de um utilizador já existente**

#### Options
![](https://i.imgur.com/ImPrf4H.png)
![](https://i.imgur.com/ym9WUrP.png)


### usermod
**Utilizado para modificar um conta de utilizador existente**

#### Options
![](https://i.imgur.com/lOPoyW9.png)
![](https://i.imgur.com/3J8pMFD.png)

### userdel
É importante reter que por default o comando **userdel username** não apaga a diretoria home do utilizador do sistema , se quisermos fazer isso temos que utilizar a option **-r** 

## Grupos Linux
Caso o sistema Linux tenha sido configurado para utilizar autenticação local os nossos grupos vão estar no ficheiro **/etc/group**

Cada registo é composto pelos seguintes : 
												**Group:Password:GID:Users**

![](https://i.imgur.com/ppKt2as.png)
![](https://i.imgur.com/v2OrofQ.png)

## Gerir grupos através da linha de comandos
### groupadd
#### Options
![](https://i.imgur.com/ayysC9b.png)

### groupmod
Utilizado para modificar um grupo , incluindo adicionar utilizadores 
#### Options
![](https://i.imgur.com/tW50Br2.png)

### groupdel

## Gerir ownership, permissões e quotas
### Gerir Ownership
Cada vez que um utilizador cria um novo ficheiro ou diretoria a sua conta é atribuída como **dona** do mesmo 
#### Como a ownership funciona
Conseguimos ver a ownership dos ficheiros utilizando o comando **ls -l**
Conseguimos **especificar** um certo utilizador como donos do ficheiro ou diretoria, para fazer isto é necessário estarmos autenticados com a conta root. Ou caso que seja para mudar qual o grupo que é dono do ficheiro ou diretoria é necessário sermos o utilizador que criou ou o root.
Isto faz-se utilizando o **chown** e o **chgrp**
##### chown
Utilizado para **mudar o utilizador ou grupo** que é **dono** de um ficheiro ou diretoria

##### chgrp
Utilizado para **mudar o grupo** que é **dono** de um ficheiro ou diretoria

### Gerir Permissões
#### Como funcionam as permissões
![](https://i.imgur.com/hq4KkSZ.png)

Cada ficheiro e diretoria no sistema Linux **guarda as permissões especificas atribuidas** ao mesmo. Estas permissões constituem o **modo do ficheiro**, estas são atribuidas às 3 entidades diferentes para cada ficheiro e diretoria no **file system**

- **Owner** -> Conta de utilizador atribuida como dono, permissões atribuidas a donos apenas se aplicam aquela conta de utilizador em especifico
- **Group** -> Grupo de utilizadores dados como donos, as permissões aplicam-se a todos os utilizadores dentro daquele grupo
- **Others** -> Todos os utilizadores que se conseguiram autenticar no sistema.

![](https://i.imgur.com/yqTihsz.png)

#### Trabalhar com permissões default

Por default o Linux atribui permissões rw-rw-rw- (666) a todos os ficheiros e diretorias criados no **file system** . Para melhorar a segurança o Linux utiliza uma variável chamada **umask** para remover automaticamente essas permissões do modo default, o valor desta variável é um número de 3 digítos.
Para a maioria das distribuições Linux o valor default do **umask** é 022.
O 1º digito refere-se ao dono , o 2º ao grupo e o 3º aos others.
Para alterações temporárias utiliza-se o comando **umask value**

#### Trabalhar com permissões especiais

- **SUID** -> 4
- **SGID** -> 2
- **Sticky Bit** -> 1
- ![](https://i.imgur.com/K6HLSbM.png)

### Implementar quotas de disco
Para implementar quotas de disco é necessário instalar o package de quotas no nosso sistema
![](https://i.imgur.com/jqCtQ4x.png)

Para ver o **espaço de disco utilizado por cada utilizador** pode-se utilizar o comando -> **repquota -av**

**Criar quotas de disco para cada utilizador** -> **edquota -u username**
**Criar quotas de disco para cada grupo** -> **edquota -g groupname**


## fim de Aula 7

# Aula 8

### Um SysAdmin previne e corrige

### Se formos SysAdmin temos de ter plano de recuperação de desastre


## O que é um desastre?
É tudo aquilo que tenha impacto significativo na habilidade de uma empresa fazer negócios. Um Desastre é um evento catastrófico que causa interrupções e afeta edificios e lugares.

## Análise de Risco - Especialistas
* O primeiro passo de um Plano de Recuperação de desastres é fazer uma análise de risco.
* Gestão de riscos pode ser feito por consultores externos
* Uma empresa pode contratar especialistas para fazer a análise de risco enquanto tem pessoal responsável pela gestão de risco

## Análise de Risco - o que é
* Uma análise de risco consiste em determinar que desastres a empresa está em risco de experenciar
* Determinar as chances desses desastres acontecerem
* A análise determina o possivel custo para a empresa por cada tipo de desastre
* A empresa usa a informação da análise de risco para decidir quanto capital é sensato despender para mitigar os efeitos de cada desastre

## Ameaças
* Físicas - Tempo, Desastres Naturais, Bombas, Falhas de energia
* Humanas - Cracking, Furto, Fraude, Suborno, Espionagem, Sabotagem e Acidentes
* Software - Virus, Cavalos de Troia, Bombas lógicas, DOS

## Proteger de Ameaças
São necessárias medidas preventivas e de controlo de danos depois das violações.
* Identificar o que estamos a tentar proteger
* Avaliar as maiores fontes de risco e onde a confiança é colocada
* Trabalhar em medidas possiveis e de custo-beneficio para os ataques


## Fórmula de Mitigação de Risco
Orçamento = (Provável custo do desastre - Provável custo da mitigação) * Risco de Desastre

## Avaliação de Risco
* Quem conhece os meus riscos?
* Quais são os meus riscos? (Existem SPFs-Single Point failures ? )
* Qual é a probabilidade de ocorrerem
* Quanto custará?
    * Listar todos os riscos e o seu custo/consequência. Rever a lista a cada ano/dois anos. Submeter à gerência com propostas de mitigação.


## Criar Plano de Recuperação de Desastre
* Listar quatro sistemas diferentes
* Listar três riscos reais para cada sistema
* Propor uma minimização para cada responsabilidade
* Propor uma mitigação para cada responsabilidade


## Exemplo de 4 sistemas
* Smartphone
* Desktop
* Servidor de Email
* Infraestrutura de Rede

## Risco de Desastre de Smartphone
* Cair na água
* Problemas de bateria
* Sobreaquecimento
* Roubo/Furto
* Quebra
* Malware/Software mal intencionado
* Bugs
* Avaria na rede
* Falta de recursos (armazenamento)
* Falta de Bateria


## Política de Segurança
* Define objetivos claros
* Demonstra um compromisso de uma empresa para a seriedade da sua segurança
* Assegura compromissos legais e contratuais
* Ramificações económicas causadas por uma falha de segurança são compreendidas.
* A política tem de ser mantida e atualizada por uma entidade responsável.


## Segurança Organizacional
* Uma equipa de segurança deve ser formada para providenciar conselhos multi-disciplinares e colocar políticas
* A equipa deve alocar responsabilidades dentro da empresa para manter a segurança dos Assets a todos os níveis
* Niveis de autorização devem ser impostos
* Deve existir um contacto com a bófia/lei e entidades reguladoras
* Qualque tipo de 'outsourcing' deve ter em conta os riscos associados com a abertura da segurança da empresa


## Classificação e Controlo de Assets
* Empresas devem ter um inventário com os seus Assets
* Cada Asset deve ser classificado com um nível de segurança apropriado
* Procedimentos de etiquetagem para processar níveis diferentes de informação (post, fax, E-mail, telephone, conversation over dinner)

## Segurança do Pessoal
* Serve para reduzir o risco do erro humano e de ataques maliciosos por furto, fraude ou vandalismo.
* Deve haver responsabilidades de Segurança
* Acordos de Confidencialidade
* Termos e Condições contratuais e de responsabilidade
* Treinar os utilizadores para eventuais ameaças
* Um plano de contigência deve ser feito e o staff familiarizado para que violações e fraquezas sejam reportadas imediatamente


## Segurança Física e do Ambiente
* Todos os sistemas devem ter uma segurança física
* Perimetro de segurança que envolve restrições físicas contra furto
* Sistema de deteção de intrusão
* Ambiente controlado e seguro
* Os equipamentos devem ser protegidos contra ameaças físicas (fogo, café, comida)
* Os equipamentos devem ter fontes de energia sem interrupção
* Tudo tem de ser limpo para não haver divulgação de informação confidencial


## Gestão de Operação e Comunicação
* A troca de Gerência deve incluir autorizações apropriadas e documentação das mudanças para análise em caso de problemas
* Procedimentos devem ser documentados para responder a todo o tipo de ameaças
* Backups, Descarte Seguro de informação e materiais devem ser integrados no esquema
* Análises e auditorias devem ser planeadas para as violações

## Controlo de Acessos
* Gestão de Utilizadores
* Gestão de Passwords
* Gestão de Chaves
* Privilegios de Acesso
* Segurança de Equipamentos sem vigilância
* Utilização de Sistemas Operativos Seguros
* Restrição de Privilégios
* Segregação de Assets independentes
* Autenticação para acesso
* Sincronização de Relógio
* BYOD

## Desenvolvimento de Sistemas e Manuntenção
* Segurança deve ser implementada nos sistemas desde a sua criação
* Validação de Input/Output
* Certificados e Assinaturas criptográficas
* Canais Secretos
* Não usar software open-source

## Continuidade de Gestão de Negócios
* Cada organização deve estimar o impacto das catastrofes e das violações de segurança

## Conformidade
* Leis e regulamentações devem ser obedecidas
* Regulação da informação pessoal e métodos criptográficos devem ser tidos em conta

## Como fazer um Plano de Recuperação de Desastres
* Medir os riscos (%)
* Quantificar os riscos ($)
* Manter os dados atualizados
* Implementar medidas de minimização de risco e testar a sua eficácia
* Implementar medidas de mitigação de desastres e testar se possivel
* Refazer


## Como se faz um plano de recuperação de desastres
* Medir e qualificar erros
* Definir e implementar minimização de riscos
* Definir e testar acções de mitigação de desastre
* Refazer


## Quem, quando, como, onde, com quê, com quem, em quanto tempo, para quê? -> determinar para cada item do plano

Se o plano não tiver estes itens, não é um plano, mas uma declaração de intenções

Perceber que serviços são críticos, quanto tempo temos, que desastres são prováveis e quanto iria custar prevenir e mitigar estes desastres.
Um plano de desastres deve ser construído com critérios pois é preciso tempo para reconstruir tudo. Quanto mais tempo precisamos, mais redudância total.

Aeronaútica - tem redundância e backup de redundância.


## Aspetos Importantes - Plano de Desastres
* O aspeto mais importante de um plano de desastre é **perceber que serviços são os mais críticos**
* Perceber quais as **restrições de tempo**
* Quais os **desastres mais prováveis** de acontecer
* Requer um **planeamento prévio**
* Procurar **maneiras simples** de limitar o dano
* **Redundância total**, inclusive um local redundante


## Minimização vs Mitigação
![](https://i.imgur.com/iReeYX4.jpg)


## fim de Aula 8



# Aula 9

## Logs
Servem para **prevenir** e **corrigir**

## Ferramentas de processamento e logs
* Alarmística
* Manutenção

## Ferramentas Forenses
* Segurança
* Identificação de Ataques

## Logs - Continuação
* Ninguém quer gerir logs
* Têm demasiada informação inútil
* Nada os substitui quando são precisos
* Apps diferentes usam sistema de logs diferentes
    * é preciso filtrar a informação para saber o que se procura

## Estratégias de Gestão de Logs
* Por omissão, os logs são escritos localmente
* Os logs podem ser feitos num servidor de logs
* Logs podem ser copiados para um servidor para análise

### Os logs servem para ajudar o SysAdmin a perceber o que se está a passar com aquele sistema em particular


## Tipos de Logs
* Informational - Servem para mostrar aos utilizadores e administradores que algo benigno aconteceu. Por exemplo, quando um sistema é reiniciado
* Debug - São geradas pelo sistema de software para ajudar os desenvolvedores a identificar os problemas e resolvê-los
* Warning - Acontecem quando coisas são precisas ou estão em falta para um sistema
* Error - Mensagens de Erro que ocorrem a vários níveis num sistema
* Alert - Servem para indicar que algo interessante aconteceu. São usados por exemplo num sistema de deteção de intrusões

### Alguns logs podem ter niveis de prioridade

### Loghost - máquina que armazena os logs

### Syslog - protocolo que transmite mensagens de logs para o Loghost

### Syslog pode ser uma aplicação para visualizar os logs do sistema

### SNMP - Simple Network Management Protocol -> Gera Logs

## O que deve conter um log
* Timestamp
* Fonte da Mensagem
* Data da Mensagem

## "Ter um plano"
* logging do quê?
* logging para quê?
* restrições legais a logging de utilizadores


### Logging é bom, mas dá trabalho, ocupa recursos, e exige mineração dos logs


### Problema de Logs -> mensagens incompletas ou não-úteis

## Utilidade dos Logs
* Gestão de Recursos(saber se um sistema está a funcionar bem/ ligado ou não)
* Deteção de Intrusões/Logins
* Resolução de Problemas
* Análise forense

### Uma mensagem de log deve corresponder a um evento

## Tipos de campos habituais numa mensagem de log
* Date/time
* Tipo de entrada de log
* Sistema que produziu o log
* Aplicação ou componente que fez o log
* Indicação de Sucesso de falha
* Severidade, prioridade ou importancia de uma mensagem de log
* Podem ser guardados os usernames de atividades relacionadas com os utilizadores

## Os 5 w's do Logging
* What happened
* When did it happen
* Where did it happen
* Who was involved
* Where he, she or it came from

![](https://i.imgur.com/f6uaqIH.png)


![](https://i.imgur.com/M6RZvRE.png)




## fim de Aula 9

# Aula 10
## VPN (Virtual Private Network)
As VPNs criptografam seu tráfego de Internet e disfarçam sua identidade online. Isso torna mais difícil para terceiros rastrear suas atividades online e roubar seus dados. A criptografia ocorre em tempo real.

## VPN Tunnel
Um "Túnel VPN" é uma conexão encriptada entre um dispositivo e o servidor VPN.

## IPSEC
Extensão do protocolo IP que providencia segurança a nível da camada IP para as comunucações da Internet.

## ACL (Acess Control List)
Regras definidas pelos SysAdmins que aceitam ou não acesso a um dispositivo de uma rede.

## ISAKMP (Internet Security Association and Key Management Protocol)
3 parâmetros:
 - encryption (ex: aes 256)
 - key share - (pre share or rsa)
 - diffie group (ex 5)
    
## Crypto Map
Define os peers, o grupo diffie-helman e endereço correspondente. Estas informações têm que ser coincidentes com as anteriores e é o que liga tudo.

## VPN Entre Router1 e Router2

1 - ACL entre router1 e router2
2 - Aplicar o ISAKMP desejado, estabelecendo a chave e os endereços dos ambos os routers.
3 - Aplicar o IPSEC para ambos os routers, com o mesmo tipo de encriptação (ex: aes 255) e de autenticação (ex: sha-hmac)
4 - Aplicar o crypto-map para ambos os routers
5 -Ligar o processo anterior ativando o crypto map anteriormente definido 

Verificação da conexão pode ser verificada através do ping
## fim de Aula 10