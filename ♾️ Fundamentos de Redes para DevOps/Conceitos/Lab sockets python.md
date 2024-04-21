----------------- SOCKET DE SERVIDOR ------------
!. IMPORTANTE- Lembrar de dar permissão de execução no arquivo 
1. editor de texto 
2. python instalado na máquina 
3. lib socket python 
4. importar a lib
5. instanciar o objeto socket
6. chamar o metodo bind passando como parametro o ip e a porta em uma tupla 
7. chamar o metodo listen 
x. aceitar a conexão e declarar as variaveis conn e addr chamando o método accept 
8. rodar o script 
9. visualziar conexão aberta com ss
10. instanciar conexão com o nc (nc -v <ip> <porta>)
11. receber os dados transitandos na conexão com o metodo recv da variavel conn passando por parametro o tamanho máximo que o pacote pode ter
12. ao printar os dados retornados dentro de um while true pelo metodo recv é necessário mudar o tipo de byte para string com o método decode
13. visualizar a conexão estabelecida com ss filtrando pela porta 

--------------- SOCKET DE CLIENTE ----------------

3,4,5. =
6. após instanciar o objeto socket acessar o método connect passando como parametro a porta aberta pelo servidor e o ip 
7. pegar a string que o usuário deseja enviar 
8. enviar a mensagem (lembrar de converter para bytes com o método encode)


ACOMPANHAR TUDO COM WIRESHARK 