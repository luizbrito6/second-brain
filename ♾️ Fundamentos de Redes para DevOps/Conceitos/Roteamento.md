-------

Para iniciar esse conceito é importante entender o funcionamento de [[Subnets]], ou seja como são segregados as redes para dividir de forma lógica. Pensando em uma empresa podemos ter uma rede para cada área (TI, financeiro, rh, entre outros), essa divisão é extremamente importante para conseguir controlar a comunicação, dependendo do cenário uma área não tem necessidade de se comunicar com outra. 

Em função disso precisamos de determinados dispositivos que conseguem realizar a comunicação entre as subnets quando necessário, daí vem o conceito de **roteamento**. 

Para realizar essa comunicação entre redes vamos usar Rotas que podem ser visualizadas em máquinas Linux com o seguinte comando: 

```bash
ip r 
```
#### Contexto do lab
-------
1. Por estar utilizando um debian é necessário configurar o ip das interfaces de rede que vão se comunicar diretamente com as Subnets que contém em cada uma, uma máquina. Segue o comando para adicionar um IP em uma interface: 

```
sudo dhclient -v <nome-interface>
```

2. Com os IPs baseado nas interfaces de rede no contexto do laboratório configurados, é necessário configurar rotas para ao chegar uma solicitação em um host x para um host y, passe pela máquina que está viabilizando a comunicação entre redes.  Por isso vamos configurar uma rota com o seguinte comando: 

``` bash
ip route add <ip-destino> via <ip-router>
```
