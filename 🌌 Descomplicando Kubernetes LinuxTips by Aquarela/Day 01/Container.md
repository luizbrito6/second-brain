--------

1. Isolamento de recursos  
2. Diferença entre container e máquina virtual 
3. O que é um cgroup?
4. O que são os namespaces do kernel? 


Um container é o de forma direta ao ponto literalmente isolamento, literalmente vamos pegar uma parte do hardware que vai ser dedicado unicamente para o  um ambiente separado, como se fosse mundos diferentes. Na questão do isolamento estamos falando literalmente de cpu, memória, interfaces de rede, usuários e memória, literalmente um cenário novo. ***Mas qual seria a diferença entre um container e uma máquina virtual?*** Pensando nessa pergunta é importante frisar um fato importante os contêineres foram feitos com uma camada de virtualização que é executada encima de um sistema operacional com o foco de ter nele somente o que é necessário para executar as dependências da aplicação declarada na imagem, sendo assim eu não preciso de 3 sistemas operacionais para executar 3 containres e sim um [[Container Engine]] e [[Container Runtime]] para executar esses processos na