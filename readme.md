# Docker com Laravel 7

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Esse projeto compartilha uma versão simples e funcional de um container com ngnix e mysql, tendo instalado na app uma versão do laravel, atualmente a versão 7!

### Baixando o projeto!
```sh
$ mkdir workspace
$ cd workspace
$ git clone https://github.com/davicervo/docker_laravel_7.git
```
### Como utilizar esse projeto!
Altere algumas informações antes de inciar esse processo...
Dentro do arquivo docker-compose.yml, as linhas 6 e 7 são obrigatórias, porém as outras são opcionais.
```sh
linha 6 -> user: davicervo (coloque o seu usuario)
linha 7 -> uid: 1001 (coloque o seu uid)
linha 10 -> image: davicervo (escolha um nome para a sua imagem)
linha 11 -> container_name: davicervo-app (escolha um nome para o seu container app)
linha 17 -> [networks]: davicervo (escolha um nome para a sua network)
linha 21 -> container_name: davicervo-db (escolha um nome para o seu container db)
linha 24 -> [MYSQL_DATABASE]: database (escolha um nome para o seu banco de dados, o mesmo do seu arquivo .env)
linha 25 -> [MYSQL_USER]: user  (escolha um nome para o seu usuario acessar banco de dados, o mesmo do seu arquivo .env)
linha 26 -> [MYSQL_PASSWORD]: password  (escolha uma senha para seu usuario acessar o banco de dados, o mesmo do seu arquivo .env)
linha 27 -> [MYSQL_ROOT_PASSWORD]: paswoord  (escolha a senha do usuario root do seu container mysql)
linha 33-> [networks]: davicervo (o mesmo nome da linha 17)
linha 35 -> [ports]: 3306:3306 (a porta escolhida precisa estar disponível)
linha 39 -> container_name: davicervo-nginx (escolha um nome para o seu container nginx)
linha 47 -> [networks]: davicervo (o mesmo nome da linha 17)
linha 50 -> [networks]: davicervo (o mesmo nome da linha 17)
```
Após essas configurações acesse a pasta do projeto...
```sh
$ cd workspace
$ docker-compose up -d
```

Para verificar o projeto rodando...

```sh
http://localhost:8000/
```