**10 bytes aleatórios**
openssl rand -hex 10
**Para AES RC4 e DES**
**AES = Advanced Encryption Standard **   -> Cifra de chave simétrica por blocos. -> Cipher Block Chaining
**RC4 = Rivest Cypher 4**
**DES**
openssl enc .... 
-e para encriptar
-d para desencriptar
-K para passar uma chave diretamente
-k para passar uma chave dentro de um file

**Para SHA , MD5, MAC e HMAC**
**SHA = Secure Hashing Algorithm**
**MD5 = Message Digest 5**
**MAC = Message Authentication Code**
**HMAC = Hashed Messaged Authentication Code**
openssl dgst ...

**Para Chaves públicas e privadas**
openssl rsautl...
**Gerar par de chaves**
openssl genrsa -out sk-and-pk.pem 1024
**Extrair chave publica**
openssl rsa -in sk-and-pk.pem -pubout -out pk-PM.pem
**Ver chave pública**
openssl rsa -in pk-PM.pem -pubin -text -noout
**Gerar chaves mas protegidas por cifra simétrica**
openssl genrsa -aes128 -out sk-and-pk.pem 1024
**Cifrar utilizando a chave publica**
openssl rsautl -encrypt -pubin -inkey pk.PM.pem -in secret.key -out secret.key.rsa
**Decifrar utilizando a chave privada**
openssl rsautl -decrypt -inkey sk-and-pk.pem -in secret.key.rsa -out secret2.key