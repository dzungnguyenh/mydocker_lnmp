# mydocker_lnmp
A docker config for Linux - Nginx - MySQL5.7 - PHP7. It is divided into 3 containers:

1. Nginx is running in `Nginx` Container, which handles requests and makes responses.
2. PHP or PHP-FPM is put in `PHP-FPM` Container, it retrieves php scripts from host, interprets, executes then responses to Nginx. If necessary, it will connect to `MySQL` as well.
3. MySQL lies in `MySQL` Container,

You have to had [Docker](https://docs.docker.com) and [Docker Compose](https://docs.docker.com/compose) installed.

## Command to start

$ docker-compose up

## Command to re-build containers

$ docker-compose build

## For more operations to containers, please refer to:

$ sudo docker-compose --help
