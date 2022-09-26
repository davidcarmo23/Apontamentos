# Lab 2
## Tarefa 1
Biblioteca de funções básicas de criptografia
### Questão 2
O OpenSSL é muito importante e (eishh!) continha um mega bug que ía acabando com a Internet.
### Questão 3
Escrevendo $ __man__ no terminal...
### Questão 4
Toolkit e comando
### Questão 5
Nunca experimentei, mas penso que sim.
### Questão 6
Claro
### Questão 7
Também dá
### Questão 8
Faz tudo
### Questão 9
Não
## Tarefa 2
openssl rand -hex 10
## Tarefa 3
Não, estamos na shell do openssl
### Questão 11
Sim
### Questão 12
48
### Questão 13
-in , -out , -pass , -e , -d , -a/-base64, -bufsize, -nopad ...

### Questão 14
 Sim
### Questão 15
Rivest Cipher 4
### Questão 16
Sim, parece
### Questão 17
Não, não funcionou. :(
### Questão 18
Sim, já verifiquei usando $ cat ciphertext.rc4 e o que lá encontrei não faz sentido nenhum
### Questão 19
- 1º -K
- 2º -k
- 3º out
- 4º in
- 5º -e
### Questão 20
openssl enc -d -rc4 -K abcdef0123456789 -in ciphertext.rc4 -out teste.txt
### Questão 21
Sim , a chave utilizada para encriptar
### Questão 22
Ao facto da mesma chave de cifra ser usada para cifrar e para decifrar.