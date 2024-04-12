
O HTTP é um protocolo de comunicação que é executado na camada de aplicação do TCP/IP, sua função é enviar dados para as camadas mais baixas e assim consequentemente chegar até o host de destino. Termos importantes desse protocolo são os headers/cabeçalhos que guardam informações importantes para entender a comunicação, como por exemplo, o host de detino, o método HTTP (que no caso é qual ação vai ser tomada com os dados solicitados ou enviados) e informações gerais como qual o navegador que está realizando a requisição. Sempre há uma solicitação e uma resposta, chamamos isso de request e response e nesses dois processos passamos por todas as camadas enviando no body os dados e informações crucais no header.


#### Métodos HTTP
---

|Método|Ação|
|---|---|
|GET|Buscar dados|
|POST|Enviar dados|

#### Response Code
---

| Code    | Função                                          |
| ------- | ----------------------------------------------- |
| 100-199 | Informações                                     |
| 200-299 | Deu tudo certo                                  |
| 300-399 | Solicitação disponível porém em outro endereço. |
| 400-499 | Deu ruim no lado do cliente                     |
| 500-599 | Deu ruim no lado do servidor                    |

#### HTTP Persistent vs Not-persistent
---
Aqui são dois termos que são um a evolução do outro. No caso a comunicação entre servidor e cliente pode ser persistente, não persistente e paralela, focando nos dois primeiros termos é necessário observar que para o ocorrer essa comunicação tem que ter uma conexão entre o servidor e o cliente, se for persistente essa conexão é feita uma única vez e as solicitações são enviadas nessa conexão aberta, no caso da não persistente é necessário abrir uma nova conexão para cada solicitação.


Pq a primeita requisição a um site pode tr