# Шпаргалка по Docker

# Содержание

   * [Установка](#installation)
   * [Docker Registries &amp; Repositories](#docker-registries--repositories)
   
# Установка

## Linux

```
sudo curl -sSL get.docker.com | sh
```
Добавляем себя в группу **docker**
```
sudo adduser username docker
```
Перезагружаемся. Запскаем контейнер “hello-world”
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

# Docker Registries & Repositories

## Login to a Registry

```
docker login
```

```
docker login localhost:8080
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
