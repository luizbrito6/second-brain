Esse curso tem como objetivo apresentar os conceitos de redes com uma camada de abstração focada para DevOps, ou seja, não é tão aprofundado como em conceitos do CCNA, esse curso está dentro do meu escopo de preparação para a certificação SA da AWS.

> [!NOTE]
>A dependência no entre as camadas é um ponto importante de se analisar, pois, por exemplo, não tem como um pacote transitar entre dois hosts se não existe o link criado na camada de enlace, ou não tem uma conexão com a internet na camada física.
## Conceitos do curso
---
- Seção 1: Camada de Aplicação
	- Essa seção do curso teve como objetivo demonstrar primeiramente o funcionamento da camada de aplicação do [[Modelo OSI]], porém logo em seguida o instrutor apresentou o conceito dando ênfase no [[TCP-IP]]. Dando continuidade a seção foi apresentado as demais camadas que vamos ver nesse curso e conceitos como o [[HTTP]], [[Proxy]], [[Cookies]] , [[DNS]], [[TLS-SSL]] entre outros que também vão ser mencionados.  
- Seção 2: Camada de transporte
	- Agora que conseguimos entender tópicos de coleta de informações da comunicação com [[HTTP]], o funcionamento da criptografia dos dados com [[TLS-SSL]] e a tradução de nome com [[DNS]] para conseguir acessar host com uma url e não um IP é necessário acessarmos a próxima camada que vem com a seguinte perguntar ***"Tá mas como esses dados vão transitar? Na camada de rede 😀"*** 
	- Um ponto importante dessa transição entre camadas é que elas são estritamente dependentes sem os processos da camada de aplicação não conseguimos chegar na camada de transporte e consequentemente na camada de rede. 
	- É aqui que vai ocorrer o estabelecimento da conexão [[TCP-IP]] e vamos ter literalmente um endereço para transitar os dados na próxima camada. 
- Seção 3: Camada de Rede
	- Certo vamos entender que passamos por todos os procedimentos na camada de aplicação e também temos uma conexão estabelecida na camada de transporte, agora na camada de rede que vamos realmente ver os dados caminhando de um ponto a outro.






