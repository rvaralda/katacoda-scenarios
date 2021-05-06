# Rodando seu primeiro container no docker

## Execute o seguinte comando:

`docker run --name webserver -d --rm -p 80:80 nginx`{{execute}}

### Verifique o container rodando 

`docker ps`{{execute}}

### Verifique as imagens dos containers

`docker images`{{execute}}


### Verificando os eventos
`docker logs -f webserver`{{execute}}
Use `ctrl+C` para fechar os logs


## Testando no navegador

Clique em `+` e `View HTTP port 80 on Host 1`

Você deverá ver a página de status do elasticsearch

## Testando no terminal

Abra um novo terminal clicando em `+` e `Open New Terminal`

E rode o seguinte comando:

`curl localhost`{{execute}}


### Removendo o container

`docker rm webserver`{{execute}}

ou

`docker rm -f webserver`{{execute}}
