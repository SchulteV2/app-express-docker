Comandos para rodar o docker

# Vai rodar o docker na porta 80

`docker run -it -p 80:80 ubuntu`

## Instalar o Node

`apt update`

`apt install curl -y`

`curl -fsSL https://deb.nodesource.com/setup_18.x | bash -`

`apt install -y nodejs`

## Instalar o nginx

`apt install nginx -y`

### Start/Restart/Stop o nginx

* `service nginx start`
* `service nginx restart`
* `service nginx stop`

### Verificar o status

`service nginx status`

## Instalar o Nano

`apt install nano`

## Configurar o Ngnix
`nano /etc/nginx/sites-available/default`

### Configuração do ngnix
```
server {
    listen 80;

    server_name localhost;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```
Depois da configuração precisa dar restart

## Copiar o projeto para dentro do container

`docker cp /path-projeto/ <container_name_or_id>:/path-dentro-do-container`

### Dar start no app

Entrar na pasta que foi copiada, e rodar:

`node app.js`# app-express-docker
