# Passo a Passo da Demo

## Preparação

```
    Instale o Docker e o Docker Compose se ainda não estiverem instalados.
    Navegue até o diretório raiz do projeto (onde está o arquivo docker-compose.yml):
```

    ```
    cd /caminho/para/seu/projeto
    ```

## Build e Inicialização dos Containers

Construa e inicie os containers executando:

docker-compose up --build

Observação:
O parâmetro --build garante que as imagens sejam construídas a partir dos respectivos Dockerfiles. O Docker Compose criará uma rede interna (app-network) e iniciará os containers node_app e nginx_proxy.


## Testando a Aplicação

Abra o navegador e acesse:

http://localhost


Resultado esperado:

Você deverá ver a mensagem:

Hello, World from Node!

O Nginx atua como proxy reverso, encaminhando as requisições para o container Node.js na porta 3000.



# Comandos Úteis no Docker

## Listar Imagens

Listar todas as imagens Docker:

docker images

## Listar Containers

Listar todos os containers (ativos e inativos):

docker ps -a

## Listar apenas os containers ativos:

docker ps

## Remover Containers

Remover um container específico (certifique-se de que ele esteja parado):

docker rm <nome_ou_ID_do_container>

## Remover todos os containers parados:

docker container prune

## Remover Imagens
Remover uma imagem específica:

docker rmi <nome_ou_ID_da_imagem>

## Remover todas as imagens não utilizadas:

docker image prune -a

## Acessar o Container via Shell

Entrar no container em execução (por exemplo, node_app):

docker exec -it node_app /bin/sh

Observação:
Se o container utilizar Bash, substitua /bin/sh por /bin/bash.

## Ver Logs dos Containers

Visualizar os logs de um container:

docker logs <nome_ou_ID_do_container>

## Parar os Containers

Parar os containers que estão rodando:

docker-compose down

## Reiniciar os Containers

Reiniciar os containers:

docker-compose restart


## Limpeza

Para remover os containers e a rede criada pelo Docker Compose:

docker-compose down


## Para remover também as imagens construídas:

docker-compose down --rmi all
