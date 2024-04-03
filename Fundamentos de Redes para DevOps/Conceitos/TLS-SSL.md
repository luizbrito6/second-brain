-----
Esse é um protocolo que é extremamente importante pensando [[Objetivos básicos de segurança em redes]] onde é possível criptografar os dados que estão transitando de uma lado para outro. 

#### O que é? 
-----
O nosso querido protocolo que garante processos de criptografia na comunicação entre servidor e cliente, importante frisar que o SSL/TLS funciona com outros protocolos como o ICMP e FTP (indo além de uma requisição HTTP). Mas o que esse protocolo resolve e porque ele é tão importante? Nesse caso, antes de 1994 o trânsito de dados era realizado de forma literal, ou seja, no processo de transição era possível visualizar os pacotes ou até mesmo modificá-los (ataque conhecido como man in the middle). Em função desse problema nasceu o SSL primeiro e posteriormente o TSL para conseguir deixar nossos dados seguros, porém bem que seria bom mudar o response com um 0 a mais em um depósito bancário kkk. Primeiro nasceu o SSL criado pela NetScape e foi lançado algumas versões do protocolo (1.0, 2.0, 3.0 e 3.1) na 3.1 foi necessário padronizar o protocolo e nasceu o TLS que também tem suas versões como a 1.0, 1.1, 1.2 e 1.3, sendo as duas primeiras, não reconhecida como segura pelos navegadores atualmente. 

Pilares de segurança que o SSL nos disponibiliza:
- Integridade dos dados
- Confidencialidade dos dados
- Autorização em caso de certificado mTLS (simétrico)


Um importante procedimento para utilização do TLS/SSL é o [[HandShake]] onde o procedimento de comunicação criptografada é acordada entre Client e Servidor