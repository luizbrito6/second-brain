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

3.  **Criar um repositório do Docker**
	Com a api do Artifact Registry ativada vamos criar o repositório onde vai ser armazenado a imagem do Docker que vamos trabalhar posteriormente, mais uma vez esse processo é possível pelo painel ou por linha de comando. Aqui mais uma vez vamos seguir com o **Cloud Shell**: 


Verificar se o Docker está sendo executado corretamente no **Cloud Shell**: 
```
docker run --rm busybox date
```

Comando para criar o repositório **( ⚠️ Atenção substituir os valores entre <>)**: 
```
gcloud artifacts repositories create <nome-repositorio> --repository-format=docker \
    --location=<local> --description="<Breve Descrição do Repositório>" \
    --project=<id-projeto>
```

Verificando se o repositório foi criado com o seguinte comando: 
```
gcloud artifacts repositories list \
    --project=<id-projeto>
```

> [!Id do projeto]
>É possível visualizar no painel inicial clicando no botão do canto superior esquerdo e também com o comando  **gcloud projects list**

Saída esperada do comando de verificação: 
![[Pasted image 20240503142330.png]]

4. Configurar autenticação 
	 Antes de enviar ou extrair imagens, configure o Docker para usar a **Cloud Shell** `gcloud` CLI e solicitações de autenticação para **Artifact Registry**. Para configurar a autenticação nos repositórios do Docker na região `us-central1`, execute o seguinte comando no **Cloud Shell**:

```
gcloud auth configure-docker \ us-central1-docker.pkg.dev
```
⚠️ Nesse caso estou usando o local us-central1

5. **Acessar uma imagem para enviar**
	 Nessa etapa vou utilizar uma imagem hello-world para exemplificar, porém em ambiente real precisamos configurar o dockerfile, realizar o build da imagem e subir ela para o Artifact Registry. 

![[Pasted image 20240503143855.png]]

6. **Marcar a imagem do repositório**
	 Aqui vamos trocar a imagem a tag da imagem para conseguir realizar o pull no  Artifact Registry, vamos começar com o comando docker tag que funciona da seguinte forma: 

```
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```

- `SOURCE_IMAGE[:TAG]`: Esta é a imagem que você deseja marcar. Você pode opcionalmente incluir uma `TAG` existente.
- `TARGET_IMAGE[:TAG]`: Este é o novo nome (e opcionalmente a tag) que você deseja aplicar à imagem.

Sendo assim nosso comando fica da seguinte forma: 

```
docker tag <id-imagem-hello-world> us-central1-docker.pkg.dev/<id-projeto>/<nome-repositorio>/<nome-imagem>:<tag>
```
**( ⚠️ Atenção substituir os valores entre <>)**
