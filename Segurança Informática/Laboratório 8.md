# Lab 8

## Tarefa 1
13 17
N = 13 * 17 = 221
o(N) = 12 * 16 = 192

e *  d =  1 % 192
5 * 77
Chave pública = pk =(5, 221)
Chave Privada = sk =77
## Tarefa 3
Usada para cifrar **chave pública**
Usada para decifrar **chave privada**
## Tarefa 4
**Gerar par de chaves**
openssl genrsa -out sk-and-pk.pem 1024
**Extrair chave publica**
openssl rsa -in sk-and-pk.pem -pubout -out pk-PM.pem
**Ver chave p**