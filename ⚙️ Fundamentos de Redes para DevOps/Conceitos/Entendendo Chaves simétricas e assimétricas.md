	-------------------

As chaves são relacionadas com o conceito de disponibilidade comentando acima e são elas responsáveis pela criptografia na rede, onde será, possível deixar nossos dados ilegíveis até eles serem traduzidos, existem dois tipos de chaves utilizadas em transações desse tipo com HTTP e TLS, no caso são simétricas e assimétricas.

- Chave simétrica
    - Esse tipo de encriptação funciona de uma forma mais direta onde os dois lados da moeda que estão se comunicando estão realizando ambos processo (encriptando os dados e descriptando), nesse caso o client e o server tem essa mesma chave, denominada chave privada e ela tem o poder de realizar tais ações. Exemplo:
        
        1. Pedro manda uma mensagem para Maria que tem um código de tradução
        2. Maria recebe a mensagem, traduz ela e encaminha uma resposta a Pedro com o mesmo algoritmo
        
        Porém tem um grande problema na primeira comunicação entre Pedro e Maria, como Pedro vai mandar o segredo para Maria sem que alguém no meio da transição também tenha acesso a esse segredo? Ai que entra outro conceito bem importante as chaves ASSIMÉTRICAS
        
- Chaves Assimétricas
    
    - Beleza finalmente entendi!!! Para começar as chaves assimétricas trabalham em pares para conseguir realizar a comunicação entre cliente e servidor. Para isso é necessário uma chave pública que vai ser utilizada por todos os clientes e uma chave privada que vai ficar guardada a “7 chaves” no servidor, com a chave pública conseguimos encriptar os dados para enviar eles ao servidor e a chave privada é a única forma de decriptar os dados enviados no mundo, sendo assim uma forma muito segura, certo? Está parcialmente correta essa afirmação, porque a gente tem um pequeno problema, e como o servidor vai mandar uma resposta para o cliente de forma encriptada se a chave pública várias pessoas tem acesso? Sendo assim o Juninho0979 poderia visualizar dados sensíveis, como um número do cartão de crédito da Mariazinha98 (pensando na linha de raciocínio contrária agora, chave privada encriptando os dados e a chave pública decriptando).
    - Para resolver esse problema a gente tem que trabalhar com dois pares de chaves assimétricas, sendo um par do servidor e um par do cliente. Como vai funcionar esse procedimento? Da seguinte forma o cliente vai conter a sua chave privada e a chave pública do servidor e ao enviar dados ele vai usar a chave pública que só a chave privada do servidor consegue decriptar e no outro lado quando o servidor enviar uma resposta ele vai usar a chave pública do cliente para encriptar e que só pode ser decriptado pela chave privada do cliente, assim a comunicação fica perfeitamente segura? Sim, porém vai gerar um problema importante de ser observado, essa comunicação acaba sendo um pouco lenta demais e acaba afetando a performance da aplicação e aí que a gente consegue unir os dois termos para produzir uma solução 100% performática e eficiente.
- Chaves Simétricas x Chaves Assimétricas
    
    - Aqui vamos utilizar os dois conceitos para solucionar a performance e segurança ao mesmo tempo, na primeira comunicação entre servidor e cliente vamos utilizar o conceito de chaves assimétricas para enviar uma das chaves simétricas para o cliente, conseguindo assim enviar de forma segura, pois a única forma de decriptar a chave é com a chave privada assimétrica do cliente, com essa chave simétrica no lado do cliente é possível ocorrer a comunicação simétrica entre as duas chaves (cliente e servidor)