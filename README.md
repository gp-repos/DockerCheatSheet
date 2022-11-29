# Шпаргалка по Docker

# Содержание

   * [Установка](#установка)
   * [Docker Registries &amp; Repositories](#docker-registries--repositories)
   
# Установка

## Linux

Скачиваем дистрибутив и запускаем установку:
```
sudo curl -sSL get.docker.com | sh
```
Добавляем себя (username) в группу **docker**:
```
sudo adduser username docker
```
Перезагружаемся. Запускаем контейнер “hello-world”:
```
docker run hello-world
```

## Mac или Windows

Скачиваем Docker Desktop по ссылке
**Mac:**
```
https://download.docker.com/mac/stable/Docker.dmg
```
**Windows:**
```
https://download.docker.com/win/stable/InstallDocker.msi
```
Подробнее про установку можно посомтреть по ссылкам [Mac](https://docs.docker.com/docker-for-mac/install/) или [Windows](https://docs.docker.com/docker-for-windows/install/)

# DOCKER RUN

```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```
```
[OPTIONS]
-it — интерактивный режим. Перейти в контейнер и запустить внутри контейнера команду
-d — запустить контейнер в фоне (демоном) и вывести его ID
-p port_localhost:port_docker_image — порты из докера на локалхост
-e «TZ=Europe/Moscow» — указываем нашему контейнеру timezone
-h HOSTNAME — присвоить имя хоста контейнеру
— link <имя контейнера> — связать контейнеры с другим
-v /local/path:/container/path/ — прокидываем в контейнер докера директорию с локальной машины
--name CONTAINERNAME — присвоить имя нашему контейнеру
--restart=[no/on-failure/always/unless-stopped] — варианты перезапуска контейнера при крэше
```

## Logout from a Registry.

```
docker logout
```

```
docker logout localhost:8080
```

## Searching an Image

```
docker search nginx
