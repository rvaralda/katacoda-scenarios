# Rodando Elasticsearch no docker

## Execute o seguinte comando: 

`docker run --name elasticsearch -d --rm -e "discovery.type=single-node" -p 9200:9200 -p 9300:9300 elasticsearch:7.12.0`{{execute}}

### Verifique o container rodando 

`docker ps`

## Testando no terminal

Abra um novo terminal clicando em "+" e "Open New Terminal"

E rode o seguinte comando:

`curl localhost:9200`{{execute}}


## Testando no navegador

Clique em "+" e "Select port to view on Host 1"

Assim que abrir uma nova pagina: coloque 9200 e clique em "Display Port"

Você deverá ver a pagina de status do elasticsearch
