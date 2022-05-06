# Aula 1
# Aula 2
# Aula 3
# Aula 4
# Aula 5
**Unicast** -> Processo de envio de um pacote de um host para um host individual
**Broadcast** -> Processo de envio de um pacote de um host para todos os host's da rede
**Multicast** -> Processo de envio de um pacote de um host para um grupo de host's especifico

## Public and Private IPv4 Adresses
**Private address blocks** -> Host's que não requerem acesso à internet podem utilizar endereços privados
![[Pasted image 20220505220458.png]]

**Shared address space addresses** 
- Not globaly routable
- Intended for use in service provider networks
- Address block is 100.64.0.0/10

## Special Use IPv4 Addresses 
**Network and Broadcast addresses** -> Dentro de uma rede o primeiro e último endereços não podem ser atribuidos
**Loopback addresses** -> 127.0.0.1 é um endereço especial que os host's usam para direcionar tráfego para si mesmos
**Link-Local addresses** -> 69.254.0.0 to 169.254.255.255 (169.254.0.0/16) são endereços que podem ser automaticamente atribuidos ao host local
**TEST-NET addresses** -> 92.0.2.0 to 192.0.2.255 (192.0.2.0/24) sãoo endereços para motivos de teste e ensino 
**Experimental addresses** -> 240.0.0.0 to 255.255.255.254 listados como reservados

## Legacy Classful Addressing

![[Pasted image 20220505221253.png]]

**Classless Addressing** -> Criou um novo standard que permitiu provedores de serviços alocar endereços IPv4 em cada address bit boundary em vez de apenas A,B,C tipo de endereço

## Assignment of IP Addresses
Feito por **Regional Internet Registries (RIRs)**

**ISP's** -> Diretamente conectadas ao backbone da internet
**Tier 2 ISP's** -> Focam-se geralmente em clientes da área de negócios
**Tier 3 ISP's** -> Fazem agrupamento de ligação à internet em conjunto com os seus contratos para os seus consumidores

## The Need for IPV6
IPV6 é previsto para ser o sucessor do IPV4, a falta de espaço dentro dos endereços IPV4 tem sido um fator motivador para a mudança
Previsões mostram que as cinco RIRs vão ficar sem endereços IPV4 entre 2015 e 2020
IPV4 tem um máximo de 4.3 biliões de endereços enquanto IPV6 são cerca de 340 undecillion
**IPV6** compõe as limitações de IPV4 e traz melhorias

## IPV4 and IPV6 coexistence
Técnicas de migração podem ser divididas em 3 categorias:
- **Dual-Stack** -> Permite que IPV4 e IPV6 coexistam dentro da mesma rede, os dispositivos correm IPV6 e IPV4 protocol stacks simultaneamente
- **Tunneling** -> Método de transportar um pacote IPV6 numa rede IPV4. O pacote IPV6 é encapsulado dentro de um pacote IPV4
- **Translation** -> Permite que dispositivos IPV6 comuniquem com dispositivos IPV4 , um pacote IPV4 é traduzido para IPV6 e vice-versa

## IPV6 Endereço Representação
	128 bits hexadecimais de comprimento 
4 bits representam 1 hexadecimail, 32 hexadecimais = 1 IPV6

**Regra Nº1** -> Omitir 0's que iniciem partes do endereço
![[Pasted image 20220506012226.png]]

**Regra Nº2** -> Omitir todos os segmentos de 0's
Os :: podem ser utilizados uma única vez num endereço para substituir uma cadeia de 0's

## IPV6 Address Types
IPV6 não tem endereços de broadcast
- **Unicast** -> Identifica unicamente um interface de um dispositivo IPV6 . Um pacote enviado para um endereço unicast é recebido pelo interface a que foi atribuído
- **Multicast** ->
- **Anycast**  ->
# Aula 6
## Protocolos para partilhar volumes
### **O que é um volume ?**
Um disco tem partições , cada partição é um volume esta divisão pode ser mais complexa e um volume pode extender-se por vários discos. 

Em **Windows** estes discos podem ser chamados por uma Letra e dois pontos (EX: C:).
Em máquinas **X** os volumes são montados numa diretoria dentro de outra com o nome de **Volumes**.

No entanto isto não assegura **Redundância de Dados** e sem isto estamos sempre em risco.

### **RAID**
Tecnologia de virtualização de armazenamento, combine vários discos fisícos em uma ou mais unidade lógica para assegurar **Redundância de Dados**.

Existem várias variações de **Raid**:
- *RAID 0*
	- Volumes "Stripped"
	- Distribui os dados pelos discos
	- Aumenta a velocidade de acesso
- *RAID 1*
	- Copia os dados entre os discos
	- Assegura redundância
- *RAID 2*. 3*, 4, 5, 6*
	- Dados "Stripped" (bit, Byte, blocos, distribuído por blocos, distribuído duplamente por blocos ) + correção de erros
- *RAID 10*
	- RAID 0 + RAID 1

 *Não é comum ser utilizado* *

**RAID implementado por Software ou Hardware**
- **OS** consegue lidar com a redundância de dados e o "Stripping"
- **HW/ Controladores HD** dedicados para fazer o trabalho pelo OS

### **Coisas que o RAID não faz**
- Não equaciona 100% do uptime
- Não substitui cópias de segurança (**Backups**)
- Não protege contra **corrupção, erros humanos ou problemas de segurança**
- Não permite necessariamente aumentar dinamicamente o **tamanho do array**
- Nem sempre é a melhor opção para **virtualização** e **high-availability failover**

**Hot Swap** - Substituir o disco sem desligar o sistema.

## Armazenamento
**Não existe solução para dados perdidos**
 Dados são o combústivel das organizações modernas. É inevitável em algum ponto perder dados.

**Razões para Perda de Dados**
- *Erros Humanos*
	- Apagar ficheiros
	- Sobreescrever ficheiros
- *Erros de Software*
	- Apagar ficheiros
	- Ficheiros Corrompidos
	- Sobreescrever ficheiros
	- Virús , trojans, ransomware....

**3 Formas básicas de armazenamento em rede**

Aparelhos dedicados para o armazenamento de um servidor.
- **NAS** (Network Attached Storage )
- **DAS** (Direct Attached Storage) 
- **SAN** (Storage Area Network)

**Exemplificação**

![[Pasted image 20220427190637.png]]

Ao longo dos anos verificamos um **aumento da necessidade de uma maior velocidade para armazenamento e rede** .

## **SAN**
É uma **rede de alta velocidade especializada e dedicada em juntar servidores e armazenamento** inclui discos, arrays de discos, ... . O **armazenamento** é separado dos **processadores**, tem **alta capacidade, disponibilidade e escalabilidade** e também **fácil configuração e reconfiguração**.

A **Fibra** é de arquitetura SAN apesar de poder utilizar outros tipos de rede.

**Benefícios**
- Consolidação de armazenamento
- Partilha de dados
- Escalabilidade não é perturbadora para o crescimento
- Backup e recuperação melhorados
- Tape Polling - 
- Movimento de dados independente do servidor e LAN
- Desempenho elevado
- Disponibilidade de clustering de servidores alta
- Integridade de dados
- Tolerância de desastres
- Facilidade de migração de dados
- Eficiente em termos de custo 

### **NAS**
- É um dispositivo dedicado para armazenamento, opera em **modo cliente/servidor** 
- Está conectadoao servidor de ficheiros via **LAN**
- Protocolo -> NFS (ou CIFS) através de uma rede de IP's
	- **Network File System** (NFS) - Unix/Linux
	- **Common Internet File System** (CIFS) - Sistema de ficheiros remotos em Windows montado no sistema local
	- **Samba** (SMB) - Linux

**Vantagens** - Sem limitações de distância
**Desvantagem** - Velocidade e latência
**Fraqueza** - Segurança


*SAN VS NAS* - Tradicionalmente
- **NAS** é utilizado para o acesso de baixo volume a uma grande quantidade de armazenamento por muitos utilizadores
- **SAN** é a solução para armazenamento de terabytes e para acesso múltiplo e simultaneo a ficheiros como streaming de áudio e vídeo.

No entanto as linhas de divisão entre as duas está a desaparecer e o facto é que ambas as tecnologias se complementam uma à outra

### **Canal de Fibra**
- Estabelecido no ambiente de sistemas aberto como o **underlining** da arquitetura de SAN
- É estruturado com camadas independentes. Existem 5 camadas, 0 é a mais baixa. As **camadas físicas** é da 0 à 2 , estas transportam os atributos físicos da rede e transporte de dados criados pelos protocolos de nível mais elevado como o SCSI , TCP/IP ou FICON.

### **Standards**

- Desenhado para o **transporte de vários protocolos** como o HIPPI, IPI, SCSI, IP, Ethernet ...
- **Full duplex médio**
- Os **canais** são estabelecidos entre o **originador** e o **respondedor**
- **Rácio de transferência** entre 100MB's até Gigabits's
- **Distância** maior que 10km (single mode fiber)
- Multi-layer stack functions (não mapeadas para o modelo OSI)

### **Camadas do Canal de Fibra**
- **FC-0**
	- Especifica o link fisico
		- Media, transmissores, recetores e conectores
	- Abrange um grande variedade de tecnologias suportadas
	- Open Fiber Control System (OFC)
- **FC-1**
	- 8B/10B encoding
		- 8 bits de dados são codificados em 10 bits de caracteres de transmissão
		- 4 caracteres de transmissão fazem uma palavra de transmissão
		- Running Disparity soma os 1's e 0's e pode ser positiva e negativa, dependendo deste valor um dos dois valores de caracteres de transmissão é escolhido para cada byte de dados para conseguir um código livre de DC
		- Um caracter especial marca o inicio de Ordered Sets (control sequences)
			- Start of Frame (SOF), End of Frame (EOF), Link Reset (LR)...
- **FC-2**
	- ![[Pasted image 20220427194411.png]]

### **Endereços de FC**

São constituidos por:
- **FC Node** - um node tem vários ports
- **FC Port** - Ponto final de um link
- **Port ID** - Endereço único de 24-bits para um port
- **In Frame Header** - tem dois fields, o endereço de transmissão e o endereço de receção

### **Nomeação e endereçamento de FC**
- Cada nodo tem por norma um interface fisíco, **N_Port**
- Cada nodo tem um **nome** de 8 bytes
- **N_Port ID** - Endereço de port de 24 bits
- Um N_Port tem uma **ligação ponto a ponto** com outro N_Port
- Um N_Port pode estar anexado a um port de fabric, **F_Port**
- A ligação entre fabric switches é via ports de expansão, **E_Ports**
- Um port de switch, se configurado para qualquer um é um port genérico, **G_Port**

![[Pasted image 20220427195555.png]]

- **FC-3**
	- Serviços para múltiplos ports num único nodo
		- Stripping de discos rigidos
		- Grupos de caça, mais do que um port responde ao mesmo alias de endereço
- **FC-4**
	- Define a aplicação de interfaces para **Upper Layer Protocols** (ULPs)
		- SCSI
		- HIPPI
		- IP
		- AAL5
		- IEEE 802.2

Redes baseadas em **Canais de Fibra** suportam 3 tipos de **topologias** :
- **Ponto a Ponto** -> é a topologia mais fácil de implementar e de administrar, a distância entre nodos pode chegar até 10km
	- ![[Pasted image 20220427223832.png]]
- **Loop** (arbitrário) - shared media -> Similar ao conceito de Ethernet partilhar, de uso raro mas principalmente para JBOD (Just a Bunch of Disks). Um protocolo de Arbitration determina quem pode aceder a media
	- ![[Pasted image 20220427223856.png]]
- **Switched** -> Funcionam de maneira semelhante aos switches tradicionais para fornecerem mais bandwith, performance escalável , maior número de dispositivos e em alguns casos um aumento de redundância. Variam em números de ports e tipos de media que suportam.
	- Vários switches podem ser ligados para formar um switch fabric capaz de suportar um maior número de servidores host e subsistemas de armazenamento.
	- ![[Pasted image 20220427224602.png]]


## IP-Based Storage Area Networks
**FC** suport vários protocolos de camadas altas, e o **SCSI** é o mais utilizados

*E IP sobre FC?*
- Acesso a dados em SAN através de IP-based servidores
- Interworking entre NAS e SAN
O **RFC 2625** trata 2 problemas
- É um esquema que encapsula pacotes de IP e ARP dentro da moldura FC(a payload)
- Procedimento para resolver o mapeamento dos endereços

## IP-SAN
### Vantagens de IP para SAN
- Tecnologia omnipresente
	- Baixo custo de aquisição
	- Soluções com base no standard
	- Comodidade económica
	- Instalada em todas as corporações
- Baixos custos de manutenção
	- Tecnologia de rede familiar e ferramentas de manutenção
	- Provada que é uma infraestrutura de transporte reliable/interoperable
- Conectividade em larga área
	- Permite replicação de dados remota e recuperação de desastres
- Viabilidade a longo prazo
	- Grande perfil de investimento R&D, roadmap sólido

### Capacidades de Redes IP

 ![[Pasted image 20220427230020.png]]

### Protocolos IP-SAN

![[Pasted image 20220427230104.png]]



### IP - Storage Area Network (SAN)
- Armazenamento de rede IP - transportar tráfico de armazenamento por IP
- Usa TCP, transporte confiável para entrega
- Pode ser utilizado para data centers locais ou aplicações de busca longa
- 2 IETF protocolos principais:
	- iSCSI - Internet SCSI -> permite aceder a armazenamento bloqueado através de um rede TCP/IP como se estivesse anexado localmente
	- FCIP - Fibre-Channel-over-IP -> utilizado para tunelar frames de canais de fibra por conexões TCP/IP

### Internet SCSI

- É um standard na indústria que permite que SCSI bloqueie protocolos I/O de serem enviados numa rede utilizando o protocolo TCP/IP
- Modo de aceder a armazenamento através de uma rede IP como se tivesse anexada localmente
- Transporta comandos de protocolo SCSI através de uma rede IP
- É a norma mantido por IETF

 