# mydocker_lnmp
A docker config for Linux - Nginx or Apache2 - MySQL5.7 - PHP7. It is divided into 3 containers:

1. Nginx or Apache2 is running as web server Container, which handles requests and makes responses.
2. PHP or PHP-FPM is put in `PHP-FPM` Container, it retrieves php scripts from host, interprets, executes then responses to Nginx. If necessary, it will connect to `MySQL` as well.
3. MySQL lies in `MySQL` Container,

You have to had [Docker](https://docs.docker.com) and [Docker Compose](https://docs.docker.com/compose) installed.

## Command to start with nginx

$ docker-compose up nginx

## Command to start with Apache2

$ docker-compose up apache2

Or you can use `docker-composer.apache2.yml` to run with Apache2 (rename it to `docker-compose.yml` of course).

## Command to re-build containers

$ docker-compose up nginx/apache2 --build

## For more operations to containers, please refer to:

$ sudo docker-compose --help
