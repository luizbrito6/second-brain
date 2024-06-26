-------
> [!NOTE]
>**Objetivo**: Comunicar duas máquinas que estão em redes diferentes através de um terceiro host agindo como roteador

Para iniciar esse conceito é importante entender o funcionamento de [[❌ Subnets]], ou seja como são segregados as redes para dividir de forma lógica. Pensando em uma empresa podemos ter uma rede para cada área (TI, financeiro, rh, entre outros), essa divisão é extremamente importante para conseguir controlar a comunicação, dependendo do cenário uma área não tem necessidade de se comunicar com outra. 

Em função disso precisamos de determinados dispositivos que conseguem realizar a comunicação entre as subnets quando necessário, daí vem o conceito de **roteamento**. 

Para realizar essa comunicação entre redes vamos usar Rotas que podem ser visualizadas em máquinas Linux com o seguinte comando: 

```bash
ip r 
```
#### Contexto do lab
-------
1. Por estar utilizando um debian é necessário configurar o ip das interfaces de rede que vão se comunicar diretamente com as Subnets que contém em cada uma, uma máquina. Segue o comando para adicionar um IP em uma interface: 

``` bash
sudo dhclient -v <nome-interface>
```

2. Com os IPs baseado nas interfaces de rede no contexto do laboratório configurados, é necessário configurar rotas para ao chegar uma solicitação em um host x para um host y, passe pela máquina que está viabilizando a comunicação entre redes.  Por isso vamos configurar uma rota com o seguinte comando: 

``` bash
sudo ip route add <ip-destino> via <ip-router>
```
Legal, agora sabemos que o cliente-1 tem que se conectar ao router para chegar no cliente-2 e também o contrário, em função disso após configurar as rotas é necessário ficar "escutando" no router as conexões que estão ocorrendo, importante lembrar que ainda não tem rotas no router para lidar com as requisições do cliente-1 e cliente-2. Segue o comando que vamos utilizar para verificar as conexões: 

``` bash
sudo tcpdump -i <interface-de-rede>
```
Rotas que vão ser configuradas: 

Client-1: ip de destino sendo o client-2 enviar para a interface de rede do debian que está na mesma rede que o client-1

Client-2: ip de destino sendo o ip do client-1 e o a via vai ter pela interface de rede do router que está na mesma rede que o client-2 

		