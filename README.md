# The Ultimate Docker Cheat Sheet

# Table of Contents

   * [Installation](#installation)
   * [Docker Registries &amp; Repositories](#docker-registries--repositories)
   
# Installation

## Linux

For more information, see [here](https://docs.docker.com/install/#server)

```
curl -sSL https://get.docker.com/ | sh
```

## Mac

For more information, see [here](https://docs.docker.com/docker-for-mac/install/)

Use this link to download the dmg.

```
https://download.docker.com/mac/stable/Docker.dmg
```
Open the downloaded file and follow the installation instructions.

##  Windows

For more information, see [here](https://docs.docker.com/docker-for-windows/install/)

Use the msi installer:

```
https://download.docker.com/win/stable/InstallDocker.msi
```
Open the downloaded file and follow the installation instructions.


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
