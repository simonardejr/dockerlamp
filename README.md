# Docker LAMP

Ambiente de desenvolvimento usando Docker Compose. Usa:

* PHP 7.4.x
* Apache 2.4
* MariaDB 10.3
* phpMyAdmin
* Redis

## Instalação

Faça o clone desse repositório e execute `docker-compose up -d`.

```shell
git clone https://github.com/simonardejr/dockerlamp.git

cd dockerlamp/

docker-compose up -d
```

Sua stack tá pronta!! Acesse `http://localhost:8000` no seu navegador.

## Configuração

_**DOCUMENT_ROOT**_

É o diretório que o Apache vai servir. O valor default é `./public`. Coloque seus arquivos dentro desse diretório.

_**ARQUIVOS DO MySQL**_

Aqui é onde fica os arquivos do MariaDB. O diretório padrão é `./lamp-src/data/mysql`.

_**VHOSTS**_

A configuração básica de vhosts do Apache fica no diretório `./lamp-src/config/vhosts`.

_**PHP.INI**_

A configuração básica do php.ini fica no diretório `./lamp-src/config/php`.

_**LOGS**_

Apache: `./lamp-src/logs/apache2`.
MariaDB (MySQL): `./lamp-src/logs/mysql`.

## Web Server

O Apache está configurado para usar a porta `8000`. você pode acessar `http://localhost:8000`.

#### Módulos do Apache

Por padrão, os seguintes módulos estão habilitados:

* rewrite
* headers

> Se desejar habilitar outros módulos, atualize o arquivo `./lamp-src/dockerfiles/webserver/Dockerfile`. Você pode abrir um PR se quiser que eu coloque novos módulos por padrão ;)

> IMPORTANTE: Você vai precisar fazer um novo build caso altere o Dockerfile. Para isso, basta executar `docker-compose build` e restartar os containers.

## Database

Esse stack vem com as seguintes credenciais:

_**SENHA DO ROOT**_

5agF56XX30101

_**BANCO**_

docker

_**USUÁRIO**_

docker

_**SENHA DO USUÁRIO**_

docker

## PHP

A versão do PHP utilizada nessa stack é a `7.4`

#### Extensões do PHP

Por padrão, os seguintes módulos estão habilitados:

* mysqli
* pdo_sqlite
* pdo_mysql
* mbstring
* zip
* intl
* mcrypt
* curl
* json
* iconv
* xml
* xmlrpc
* gd

> Se desejar habilitar outros módulos, atualize o arquivo `./lamp-src/dockerfiles/webserver/Dockerfile`. Você pode abrir um PR se quiser que eu coloque novos módulos por padrão ;)

> IMPORTANTE: Você vai precisar fazer um novo build caso altere o Dockerfile. Para isso, basta executar `docker-compose build` e restartar os containers.

## phpMyAdmin

O phpMyAdmin está configurado para usar a porta `8080`. Use as seguintes credenciais.

http://localhost:8080/
username: root
password: 5agF56XX30101

## Redis

O redis está configurado para usar a porta `6379`.

---------

Highly inspired on [docker-compose-lamp by SprintCube](https://github.com/sprintcube/docker-compose-lamp)