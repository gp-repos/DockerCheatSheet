# Шпаргалка по Docker

# Содержание

   * [Установка](#установка)
   * [Запуск контейнера](#Запуск-контейнера)
   
# Установка

## Linux

Скачиваем дистрибутив и запускаем установку:
```
sudo curl -sSL get.docker.com | sh
```
Добавляем себя [**username**] в группу **docker**:
```
sudo adduser username docker
```
Перезагружаемся. Запускаем контейнер “hello-world”:
```
docker run hello-world
```

## Mac или Windows

Скачиваем Docker Desktop по ссылке [Mac](https://download.docker.com/mac/stable/Docker.dmg) или [Windows](https://download.docker.com/win/stable/InstallDocker.msi). 
Запускаем установщик. Следуем инструкциям. Подробнее про установку можно посмотреть по ссылкам [Mac](https://docs.docker.com/docker-for-mac/install/) или [Windows](https://docs.docker.com/docker-for-windows/install/)

# Запуск контейнера

## DOCKER RUN
```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

## OPTIONS:
    -it, -i -t                        Интерактивный терминал. Перейти в контейнер и выполнить
                                      внутри команду. Команда указывается после названия IMAGE, 
                                      например, SH - запускает shell внутри контейнера
    -d, --detach                      Запустить контейнер в фоне (демоном)
    -p external_port:internal_port    Маппинг портов внешний:внутренний
    --name CONTAINERNAME              Присвоить имя контейнеру
    -h, --hostname HOSTNAME           Присвоить имя хоста контейнеру
    -v /local/path:/container/path/   Маппинг локальной папки к папке внутри контейнера
    -e, --env «TZ=Europe/Moscow»      Задаем переменную окружения внутри контейнера,
                                      например, таймзону
    --link <имя контейнера>           Связать контейнер с другим контейнером
    --restart=on-failure              Варианты перезапуска контейнера:
                                      no/on-failure[:max-retries]/always/unless-stopped
    
## ПРИМЕРЫ:
```
docker run -d -p 8080:80 nginx
```
Скачивает (если нет локально) и запускает (run) образ nginx в фоновом режиме (-d), делает меппинг портов (-p) с порта 8080 локальной машины, на порт 80 внутри контейнера. 

# Работа с контейнерами
Список запущенных контейнеров:
```
docker ps
```
Список запущенных и остановленных контейнеров:
```
docker ps -a
```
Удалить все остановленные контейнеры:
```
docker container prune
```
Список локальных образов:
```
docker images
```
Вывести всю информацию о контейнере:
```
docker container inspect [CONTAINERNAME or CONTAINERID]
```
Вывести IPAddress, как часть информации о контейнере:
```
docker container inspect --format '{{ .NetworkSettings.IPAddress }}' [CONTAINERNAME or CONTAINERID]
```
