
1. O cliente vai enviar uma mensagem para o servidor com a flag SYN ativado, ou seja, com valor 1 e um número randômico que vai ser utilizado na conexão (esse número é exclusivo do cliente); 
3. O servidor vai responder com o seu número randômico, as flags SYN e ACK ativadas e o número de confirmação ACK que é o número randômico do cliente + 1;
4. No terceiro e último passo é necessário o cliente responder a última mensagem do servidor, somente com a flag ACK ativada, o número sequecial enviado pelo servidor + 1, o número ACK que é o somando na segunda etapa e a conexão assim foi estabelecida; 
