# Aula 1
# Aula 2
# Aula 3
# Aula 4
# Aula 5
# Aula 6

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

## Filesystems


