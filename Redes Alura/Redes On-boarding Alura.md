---------------


1. Como eu consigo visualizar o IP da minha máquina? 
```
ip addr
```

2. Uma forma de pegar uma interface de rede específica:
```
ip addr show eth0
```

A saída desse comando dá informações importantes para gente, o ponto mais legal que eu achei foi a interface de rede loopback que é utilizada para desenvolver soluções de uma forma que o host funcione como cliente e servidor. 

Outro ponto legal é que com esse comando é possível visualizar o ip privado da minha máquina, no meu caso uma vm que está rodando na azure . 
#### Endereçamento e máscaras de rede 
-------
Através da máscara de rede é possível conseguir informações importantes como o ip do [[broadcast]], o número de hosts disponíveis na rede, o ip da própria rede e através dessas informações conseguimos dimensionar tópicos como calculo de subnets. 


#### O que é o gateway da rede?
------

```
ip route 
```


A uma rfc que informa quais são os endereços privados, sendo assim existe uma faixa específica de ips que está destinada a ser usada localmente, sem se comunicar com a internet diretamente. 

[RFC 1918: Address Allocation for Private Internets (rfc-editor.org)](https://www.rfc-editor.org/rfc/rfc1918)

| 10.0.0.0        -   10.255.255.255  (10/8 prefix)       |
| ------------------------------------------------------- |
| 172.16.0.0      -   172.31.255.255  (172.16/12 prefix)  |
| 192.168.0.0     -   192.168.255.255 (192.168/16 prefix) |

Mas é importante ter cuidado, pois mesmo que o ip comece com uma dessas faixas, (10, 172, 192) ele pode ser público, em função disso é sempre bom consultar o site https://jodies.de/ipcalc para visualizar a faixa de ip disponível para determinada máscara. 

#### Resolvendo nomes com DNS
------

```
nslookup 
```

Tópicos conceituais relacionados a [[DNS]] no curso de [[Fundamentos de Redes para DevOps]]

Diferentes servers DNS retornam ips diferentes, ou seja, um método de ter escalabilidade e segurança. 

Vamos para uma abordagem mais prática com acessando o arquivo /etc/resolve.conf podemos informar qual o nosso servidor dns, podendo ser um local com o ip que conseguimos através do comando dig: 

![[saida-dig.png]]

Para fazer um teste de resolução de nomes locais podemos realizar uma modificação no arquivo /etc/hosts onde podemos visualizar uma tabela de resolução de nomes: 

![[arquivo-etc-hosts.png]]

#### Enviando e recebendo pacotes 
-------
Primeiro ponto que eu achei interessante, ao "pingar" entre redes diferentes a gente vai ter a ação do roteador, porém ao pingar entre hosts que estão na mesma rede não tem ação do mesmo. 

Com ping utilizamos o protocolo [[ICMP]] e com traceroute podemos investigar de forma mais profunda definindo o protocolo. Outro ponto importante é que ao pingar em um host e ele retornar ou não algo não significa que um site está no ar, pode ser um diagnóstico precipitado, pois pode ser somente um bloqueio desse protocolo no firewall. 

O legal desse comando traceroute (tracert no windows) é que podemos mapear em quais partes do mundo nosso pacotes estão transitando, por quantos roteadores temos que passar para que nossa solicitação cliente chegue até o servidor que vai prover nosso dado necessário. 

![[mapa-traceroute.png]]

Um grande amigo quando estamos pensando em visualizar testes de conexão é o telnet, antigamente utilizado como protocolo de transição de dados (hoje é usado o tcp e udp), porém caiu eu desuso em função da falta de segurança. No telnet a gente tem que especificar em qual porta estamos tentando acessar e no linux tem um arquivo bem legal onde conseguimos visualizar as principais portas e em quais protocolos utilizamos elas, por exemplo, 80 para o [[HTTP]], esse arquivo fica na pasta etc e seu nome é services, podemos acessar ele com o vim ou cat. 

### Curl
---

Ferramenta onde é possível interagir com APIs por linha de comando, por exemplo, aqui onde é executado uma requisição para o endpoint passado com o método GET:

```jsx
curl <url> 
```

O comando curl recebe algumas flags para lapidar o saída do comando, como por exemplo, quando é retornado um JSON podemos utilizar o jq (necessário instalar o recurso previamente) no linux para formatar a saída com os dados indentado:

```jsx
curl <url> | jq
```

Mas como eu consigo acessar os headers dessa requisição? Através de uma flag -Is no comando curl: 

```jsx
curl -Is <url> 
```
Para limpar a saída e conseguirmos em específico o response code na requisição podemos utilizar a seguinte variação do comando: 

```jsx
curl -Is <url> | head -n 1 
```
