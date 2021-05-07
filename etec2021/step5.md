# Rodando um container de elasticsearch
---

## Criando a rede de containers

`docker network create search-network`

## Criando os containers

#### Container Elasticsearch

```bash
docker run -d --name es \
--net search-network \
-e "discovery.type=single-node" \
-p 9200:9200 -p 9300:9300 \
elasticsearch:7.12.0
```

#### Container search-go

```bash
docker run -d --name search-go \
--net search-network \
-e "ELASTICSEARCH_URL=http://es:9200" \
-p 9000:9000 search-go
```

```bash
docker run -d --name search-go-slim \
--net search-network \
-e "ELASTICSEARCH_URL=http://es:9200" \
-p 9001:9000 search-go:slim
```


### Verifique os containers rodando 

`docker ps`{{execute}}

### Verifique as imagens dos containers

`docker images`{{execute}}

### Verificando os eventos
`docker logs elasticsearch`{{execute}}

`docker logs search-go`{{execute}}

`docker logs search-go-slim`{{execute}}

## Testando no navegador

`docker logs -f search-go`

Clique em "+" e "Select port to view on Host 1"

Assim que abrir uma nova pagina: coloque 9000 e clique em "Display Port"

Abra a página e inclua: `/index` ou `/search/luke`

Use `ctrl+C` para fechar os logs.

## Testando no terminal

Abra um novo terminal clicando em "+" e "Open New Terminal"

E rode os seguintes comando:

`curl localhost:9000`{{execute}}
`curl localhost:9001`{{execute}}

### Testando os comandos

#### Index
`curl localhost:9000/index`{{execute}}

#### Search
`curl localhost:9000/search/luke`{{execute}}

### Verificando novamente os eventos
`docker logs search-go`{{execute}}

## Removendo os containers

`docker rm -f search-go search-go-slim es`{{execute}}
