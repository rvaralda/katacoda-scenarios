# Rodando um container de elasticsearch
---

## Clonando o repositório

`git clone https://github.com/rvaralda/search-go.git`{{execute}}

`cd search-go`{{execute}}

## Verificando o arquivo de configuração do docker

`cat Dockerfile` ou veja na aba `IDE`

## Montando o container da aplicação

`docker build -t search-go .`{{execute}}

`docker images`{{execute}}

## Rodando o container

`docker run -d --name search-go -p 9000:9000 search-go`{{execute}}

### Verifique o container rodando 

`docker ps`{{execute}}

### Verificando os eventos do container
`docker logs search-go`{{execute}}

# Container versão leve

## Verificando o arquivo de configuração do container versão leve

`cat Dockerfile.slim` ou veja na aba `IDE`


## Montando o container da aplicação versão leve

`docker build -f Dockerfile.slim -t search-go:slim .`{{execute}}

`docker images`{{execute}}

## Rodando o container versão leve

`docker run -d --name search-go-slim -p 9001:9000 search-go:slim`{{execute}}

### Verifique o container versão leve rodando 

`docker ps`{{execute}}

### Verificando os eventos do container versão leve
`docker logs search-go-slim`{{execute}}

## Testando no terminal

Abra um novo terminal clicando em "+" e "Open New Terminal"

E rode os seguintes comando:

`curl localhost:9000`{{execute}}
`curl localhost:9001`{{execute}}

### Testando os comandos

#### Index
`curl localhost:9000/index`{{execute}}

#### Search
`curl localhost:9001/search/luke`{{execute}}

Deverá retornar um erro.

### Verificando novamente os eventos

Para entender o que aconteceu:
`docker logs search-go`{{execute}}
`docker logs search-go-slim`{{execute}}

## Removendo os containers

`docker rm -f search-go search-go-slim`{{execute}}
