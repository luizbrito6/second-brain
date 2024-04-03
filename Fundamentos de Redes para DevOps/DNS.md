
- Tradutor de nomes
    - A principal função do DNS é literalmente traduzir nomes em IPs facilitando assim o acesso a sites na internet. Funciona mais ou menos como uma agenda telefônica.
- Hosting Aliasing
    - Assim como é possível traduzir domínios em IPs, também é possível traduzir um domínio x em um domínio y, facilitando assim (estou supondo), um cenário onde já tem um DNS configurado em um serviço PaaS na nuvem e eu quero utilizar um domínio mais efetivo para o meu negócio.
- Mail server aliasing
    - Assim como a tradução de IPs de servidores web também é possível traduzir os IPs de servidores de e-mail, deixando assim a comunicação mais profissional e eficiente. Por exemplo meu e-mail da Aquarela.
- Load Balancing
    - Outra coisa legal de se fazer com o DNS é fazer ele responder para mais de um IP, fazendo assim uma distribuição de carga.

## Como funciona a busca usando DNS?

---

Para iniciar esse processo é necessário entender que um domínio é quebrado por partes e cada parte vai remeter a uma fase da nossa tradução. Para funcionar precisamos que fique alocado as informações de tradução, daí que vem os três níveis: Root Servers, TLDS e autorizativos. Na primeira fase sempre vamos buscar no server root e nele vamos conseguir quebrando o ip a informação para retornar para o cliente o próximo servidor que está ocorrendo a tradução, esse ip retornando nessa fase é o do TLD (.br, .com, .io), dentro desses servidores ocorre mais uma fase no processo de tradução, onde mais uma vez a url vai ser quebrada e vamos conseguir o ip do servidor autorizativo, na terceira fase de comunicação conseguimos analisar que no último servidor e na ultima parte do domínio é onde vai ser retornado o IP do servidor que é traduzido no pelo DNS.

### DNS Records

---

|A|Tradução de um domínio para um IP|
|---|---|
|NS|retorna os servidores autorizativos do domínio|
|CNAME|Alias ou apontar um domínio em outro domínio|
|MX|Retorna o servidor de e=mail|
|PTR|Tradução de um IP para um domínio|

### Troubleshooting DNS com dig

---

O dig é uma ferramenta do linux onde é possível realizar testes e obter informações sobre o funcionamento da tradução de nomes em IPs, ou seja, o famoso DNS.

```bash

 -- Instalando a ferramenta no linux
sudo apt install dnsutils

-- Comando base do dig 
dig @ip url <dns-record>

-- Para limpar a saída do comando 
dig @ip url <dns-record> +short 

-- Para testar baseado em um servidor DNS diferente 
dig @ip-server-dns url <dns-record>
```

Importante frisar que você pode passar uma url ou um ip.