----------

Para começar essa documentação é importante frisar o ambiente onde vai ser excutando: 

> No painel do GCP vamos executar os comandos pelo **Cloud Shell**, onde vai ser provisionando o ambiente para conseguirmos realizar os comandos necessários nesse laboratório. 

1. **Criar um Projeto** 
	Necessário ter um projeto para realizar o procedimento no caso aqui vou criar com o seguinte comando: 

```
gcloud projects create <PROJECT_ID>
```

Em que PROJECT_ID é o código do projeto que você quer criar. Um ID do projeto precisa começar com uma letra minúscula e deve conter apenas letras ASCII, dígitos e hifens e deve ter entre 6 e 30 caracteres. ***O comando não tem os sinais de maior e menor, é somente para destacar o que tem que ser editado*** 

2. **Ativar a API do Artifact Registry.**
	 Esse processo é necessário para conseguirmos executar os comandos via Cloud Shell que vão criar e armazenar nossas imagens no Artifact Registry, é possível realizar a ativação pelo painel, porém aqui vamos utilizar o seguinte comando: 

```
gcloud services enable artifactregistry.googleapis.com
```

3.  Criar um repositório do Docker
	Com a api do Artifact Registry ativada vamos criar o repositório onde vai ser armazenado a imagem do Docker que vamos trabalhar posteriormente, mais uma vez esse processo é possível 
