Esse processo funciona em várias etapas primeiro é necessário entender o que está dissertado aqui [[Entendendo Chaves simétricas e assimétricas]] , para assim realizarmos o processo do hadshake, basicamente aqui é um aperto de mãos entre o cliente e o  servidor para conseguirmos uma comunicação criptografada, a primeira etapa é o [[3-Way TCP handshake]] onde vamos ter uma comunicação inicial, 


Passo 01 - No primeiro passo o cliente vai enviar um "Hello World" para o servidor informando quais versões do TLS ele tem suporte e um conjunto de cifras que estão disponíveis.
Passo 02 - O servidor responde o cliente com o certificado TLS que contém a chave pública do servidor e informações extremamente importantes como a CA ou autoridade certificadora que garante que o certificado é válido para os navegadores. 
