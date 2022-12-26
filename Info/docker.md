# Docker

Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package.

Using Docker, you can run and manage applications in a standardized, isolated environment on your own computer or in the cloud. This makes it easier to develop and test applications, as well as deploy them to production environments.

With Docker, you can run multiple applications on the same host without them interfering with each other. This is because each container runs in its own isolated environment, with its own system libraries and dependencies. This makes it easy to run applications that might have different system requirements on the same host.

Overall, Docker makes it easier to develop, test, and deploy applications by providing a standardized and isolated environment for them to run in.

## Commonly used Docker commands

Here is a list of some of the most commonly used Docker commands:

1.  `docker run`: Run a container from a Docker image.
2.  `docker start`: Start a stopped container.
3.  `docker ps`: List running containers.
4.  `docker rm`: Remove one or more stopped containers.
5.  `docker stop`: Stop a running container.
6.  `docker pull`: Pull a Docker image from a registry (such as Docker Hub).
7.  `docker push`: Push a Docker image to a registry.
8.  `docker build`: Build a Docker image from a Dockerfile.
9.  `docker exec`: Run a command in a running container.
10.  `docker logs`: View the logs of a running container.


These are just a few examples of the many commands available in Docker. To see a complete list of Docker commands, you can use the `docker` command with the `--help` flag. For example: `docker --help`

## docker run command

The `docker run` command is used to create and run a new container from a Docker image. It has a number of optional parameters that can be used to customize the behavior of the container.

Here are some examples of optional parameters that can be used with the `docker run` command:

-   `-d`: Run the container in detached mode, which means that the container will run in the background and the command prompt will be returned to the user.
-   `-p`: Publish one or more ports from the container to the host. For example, `-p 8080:80` would publish port 80 in the container to port 8080 on the host.
-   `--name`: Assign a name to the container.
-   `-e`: Set environment variables in the container.
-   `-v`: Mount a volume from the host into the container.
-   `--rm`: Automatically remove the container when it exits.
-   `--link`: Add a link to another container.
-   `--network`: Connect the container to a Docker network.

### Examples of docker run command

Here are a few examples of the `docker run` command:

Run an interactive shell in a container based on the `alpine` image:

    docker run -it alpine sh

Run a web server in a container based on the `nginx` image, publishing port 80 in the container to port 8080 on the host:

    docker run -d -p 8080:80 nginx

Run a container based on the `mysql` image, setting the root password and creating a new database:

    docker run -e MYSQL_ROOT_PASSWORD=mypassword -e MYSQL_DATABASE=mydatabase mysql

Run a container based on the `redis` image, mounting a host directory as a volume in the container:

    docker run -v /host/dir:/container/dir redis

Run a container based on the `ubuntu` image, connecting it to an existing Docker network:

    docker run --network mynetwork ubuntu

These are just a few examples of the many different ways that the `docker run` command can be used. The options and arguments passed to the command will depend on the specific requirements of the container being run.

## docker start command

The `docker start` command is used to start one or more stopped containers.

    docker start [OPTIONS] CONTAINER [CONTAINER...]
    
It has the following options or parameters:

-   `--attach`: Attach to the container's standard output and error streams and forward signals.
-   `--detach-keys`: Override the key sequence for detaching a container.

To start a container you need to provide the container ID or name as an argument to the `docker start` command.

Note that the `docker start` command will only start a stopped container. If the container is already running, the command will have no effect and will return an error message.

Here are a few examples of using the `docker start` command:

Start a container with the name "my_container":

    docker start my_container

Start a container with the ID "abc123":

    docker start abc123

Start all stopped containers:

    docker start $(docker ps -aq)

Start multiple stopped containers:

    docker start container1 container2 container3

Start a stopped container and attach to its output and error streams:

    docker start --attach my-container

## docker stop command

The `docker stop` command is used to stop one or more running containers.
    
    docker stop [OPTIONS] CONTAINER [CONTAINER...]

 It has the following options or parameters:

-   `--time`: The number of seconds to wait for the container to stop before killing it. The default value is 10 seconds.

To stop a running container, you need to provide the container ID or name as an argument to the `docker stop` command.

Note that the `docker stop` command will only stop a running container. If the container is already stopped, the command will have no effect and will return an error message.

Here are a few examples of using the `docker stop` command:

Stop a container with the name "my_container":

    docker stop my_container

Stop a container with the ID "abc123":

    docker stop abc123

Stop all running containers:

    docker stop $(docker ps -q)

Stop multiple running containers:

    docker stop container1 container2 container3

Stop a running container and wait 15 seconds before killing it:

    docker stop --time 15 my-container
