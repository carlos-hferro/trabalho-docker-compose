# Trabalho - Docker e Docker Compose

## O que é Docker?

## Docker

Docker é uma plataforma utilizada para desenvolver, distribuir e executar aplicações. Sua principal função é permitir que a aplicação seja executada de forma padronizada em diferentes ambientes, facilitando o desenvolvimento, os testes e a implantação dos sistemas.

## O que são Containers?

## Containers

Containers são ambientes isolados utilizados para executar aplicações. Eles armazenam tudo o que é necessário para o funcionamento do sistema, como arquivos, bibliotecas e dependências, garantindo que a aplicação seja executada da mesma forma em diferentes ambientes.

## Diferença entre Imagem e Container

## Imagem e Container

Uma imagem é um modelo utilizado para criar containers. Ela contém as configurações, arquivos e dependências necessárias para executar uma aplicação.

Já o container é a execução dessa imagem. Ele funciona como um ambiente isolado onde a aplicação é executada de forma segura e independente.

## O que é um Dockerfile?

## Dockerfile

Dockerfile é um arquivo de texto utilizado para definir como uma imagem Docker será criada. Nele são descritas as configurações, dependências e comandos necessários para preparar o ambiente onde a aplicação será executada.

Algumas dessas configurações podem incluir:

* Imagem base
* Dependências
* Arquivos da aplicação
* Variáveis de ambiente
* Comandos de inicialização

Exemplo:

```dockerfile
FROM node:20
WORKDIR /app
COPY . .
RUN npm install
CMD ["npm", "start"]
```

## O que é Docker Compose?

Docker Compose é uma ferramenta utilizada para gerenciar vários containers por meio de um único arquivo de configuração chamado `docker-compose.yml`.

Com ele, é possível definir e executar diferentes serviços de uma aplicação, como servidores web e bancos de dados, de forma automatizada. Isso facilita a configuração do ambiente, reduz o trabalho manual e ajuda a evitar erros durante a implantação.


## Exemplo de Docker Compose

```yaml
services:
  app:
    build: .
    ports:
      - "3000:3000"

  db:
    image: mysql:8
    environment:
      MYSQL_ROOT_PASSWORD: root
```
Nesse exemplo, o Docker Compose configura dois serviços: uma aplicação (app) e um banco de dados MySQL (db). A aplicação será executada na porta 3000 e o banco de dados utilizará a imagem oficial do MySQL com a senha de administrador definida pela variável de ambiente.

## O que acontece quando executamos docker compose up?

O comando `docker compose up` é utilizado para criar e iniciar os containers definidos no arquivo `docker-compose.yml`.

Ao ser executado, ele verifica os serviços configurados, cria ou recria os containers necessários e inicia todos eles automaticamente. Além disso, caso existam serviços dependentes, eles também serão iniciados.

Esse comando facilita a execução da aplicação, pois permite iniciar todo o ambiente com apenas uma instrução.

## Conclusão

Docker é uma ferramenta essencial para o desenvolvimento moderno, pois facilita a criação e distribuição de aplicações. Já o Docker Compose simplifica a execução de múltiplos containers, tornando o ambiente mais organizado e fácil de reproduzir.

## Referências

DATA HACKERS. O que é Docker e para que serve.
Disponível em: https://www.datahackers.news/p/o-que-e-docker-e-para-que-serve

DOCKER. Compose Application Model.
Disponível em: https://docs.docker.com/compose/intro/compose-application-model/

SERVERSPACE. O que é um Dockerfile? Guia passo a passo para escrever um Dockerfile.
Disponível em: https://serverspace.com.br/support/help/o-que-e-um-dockerfile-guia-passo-a-passo-para-escrever-um-dockerfile/
