-------

> [!NOTE]
>O ambiente desse laboratório é uma máquina linux com um editor de texto e com o python instalado. 

> ***Vamos utilizar a lib socket do python e o primeiro processo importante é entender qual família vamos utilizar, nesse caso a de rede AF_INET, passando uma tupla com dois parâmetros (host, porta)***

| Método | Função                 |
| ------ | ---------------------- |
| recv   | recebendo dados        |
| send   | enviado dados          |
| bind   | informando o endereço  |
Ao inicializar o server com o AF_INET temos que informar qual tipo de conexão vai ser realizada 

> [!SOCK_STREAM]
>Acessar o manual de socket do linux para entender o método que identifica o protocolo de conexão. 

1. Creating Socket na documentação 