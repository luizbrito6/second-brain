-------

> [!NOTE]
>O ambiente desse laboratório é uma máquina linux com um editor de texto e com o python instalado. 

> ***Vamos utilizar a lib socket do python e o primeiro processo importante é entender qual família vamos utilizar, nesse caso a de rede AF_INET, passando uma tupla com dois parâmetros (host, porta)***

| Método | Função                                                                |
| ------ | --------------------------------------------------------------------- |
| recv   | recebendo dados                                                       |
| send   | enviado dados                                                         |
| bind   | informando o endereço                                                 |
| listen | aguando uma conexão                                                   |
| accept | retorna a conexão e o host que acessou a porta configurada no address |
Ao inicializar o server com o AF_INET temos que informar qual tipo de conexão vai ser realizada 

> [!SOCK_STREAM]
>Acessar o manual de socket do linux para entender o método que identifica o protocolo de conexão. 

Ao inicializar o código temos que dizer ao linux que o arquivo vai ter que ser executado pelo python, o nome desse procedimento é **shebang line**, onde vamos dizer ao so qual o interpretador do arquivo. 

O primeiro passo é instanciar a classe socket e nesse caso temos que passar por parâmetro a família e o tipo de conexão. Após isso vamos trabalhar com o método bind que precisa de um endereço e uma porta, uma tupla que é nomeada adress na documentação; 

Agora vamos realizar a conexão de fato com o método accept, esse método depende de dois outros processos, a conexão disponibilizada pelo método bind que passa como endereço o ip e a porta onde vai ser possível se conetar e a chamada do método listen que vai inicializar a conexão.

> [!Permissão de execução]
> Como estamos trabalhando com linux é necessário que o usuário que estamos ultilizando tenhja