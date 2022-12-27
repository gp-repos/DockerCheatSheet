# Docker

Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package.

Using Docker, you can run and manage applications in a standardized, isolated environment on your own computer or in the cloud. This makes it easier to develop and test applications, as well as deploy them to production environments.

With Docker, you can run multiple applications on the same host without them interfering with each other. This is because each container runs in its own isolated environment, with its own system libraries and dependencies. This makes it easy to run applications that might have different system requirements on the same host.

Overall, Docker makes it easier to develop, test, and deploy applications by providing a standardized and isolated environment for them to run in.

## Commonly used Docker commands

Here is a list of some of the most commonly used Docker commands:

1.  `docker run`: Run a container from a Docker image.
2.  `docker start`: Start a stopped container.
3.  `docker stop`: Stop a running container.
4.  `docker ps`: List running containers.
5.  `docker rm`: Remove one or more stopped containers.
6.  `docker image`: Manage Docker images.
7.  `docker container`: Manage Docker containers.
8.  `docker exec`: Run a command in a running container.
9.  `docker build`: Build a Docker image from a Dockerfile.
10. `docker logs`: View the logs of a running container.
11. `docker pull`: Pull a Docker image from a registry (such as Docker Hub).
12. `docker push`: Push a Docker image to a registry.

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

## docker ps command

The `docker ps` command is used to list the running containers on a host.

    docker ps [OPTIONS]
    
 It has the following options or parameters:

-   `--all`: Show all containers, including stopped ones. By default, `docker ps` only shows running containers.
-   `-a` or `--size`: Show the sizes of the containers.
-   `-f` or `--filter`: Filter the output based on the provided conditions. Multiple filters can be used by providing a comma-separated list.
-   `--format`: Pretty-print the output using a Go template.
-   `-l` or `--latest`: Show the latest created container. This includes all states (running, stopped, etc.)
-   `--no-trunc`: Do not truncate the output.
-   `-n` or `--last`: Show the last `n` created containers. This includes all states.
-   `--quiet` or `-q`: Only display the numeric IDs of the containers.
-   `-s` or `--size`: Show the sizes of the containers.

You can use any combination of these options to list the containers in the desired format. For example, `docker ps --all --size` will show all containers with their sizes.

Here are a few examples of using the `docker ps` command:

List all running containers:

    docker ps

List all containers, including stopped ones:

    docker ps --all

Show the sizes of all running containers:

    docker ps --size

Show the last 5 created containers:

    docker ps --last 5

Show the latest created container:

    docker ps --latest

Filter the output to show only the containers with a specific name:

    docker ps --filter "name=my-container"

Filter the output to show only the containers with a specific label:

    docker ps --filter "label=env=production"

Pretty-print the output using a Go template:

    docker ps --format "table {{.ID}}\t{{.Names}}\t{{.Status}}"

## docker rm command

The `docker rm` command is used to remove one or more containers.

    docker rm [OPTIONS] CONTAINER [CONTAINER...]

It has the following options or parameters:

-   `--force` or `-f`: Force the removal of a running container. This sends a SIGKILL signal to the container, which terminates it.
-   `--link`: Remove the specified link.
-   `--volumes` or `-v`: Remove the volumes associated with the container.

To remove a container, you need to provide the container ID or name as an argument to the `docker rm` command. You can remove multiple containers by specifying their IDs or names as a space-separated list.

Here are a few examples of using the `docker rm` command:

Remove a stopped container:

    docker rm my-container

Remove a running container:

    docker rm --force my-container

Remove multiple stopped containers:

    docker rm container1 container2 container3

Remove a container and its associated volumes:

    docker rm --volumes my-container

Remove a link:

    docker rm --link my-link
    
## docker image command

The `docker image` command is used to manage Docker images. It has the following options or parameters:

    docker image COMMAND

It has the following options or parameters:

-   `build`: Build an image from a Dockerfile.
-   `history`: Show the history of an image.
-   `import`: Import the contents from a tarball to create a filesystem image.
-   `inspect`: Display detailed information on one or more images.
-   `load`: Load an image from a tar archive or standard input.
-   `ls`: List images.
-   `prune`: Remove unused images.
-   `pull`: Pull an image or a repository from a registry.
-   `push`: Push an image or a repository to a registry.
-   `rm`: Remove one or more images.
-   `save`: Save one or more images to a tar archive.
-   `tag`: Create a tag that refers to an image.

Each subcommand has its own set of options and parameters. You can use the `docker image <subcommand> --help` command to see the options and parameters for a specific subcommand.

Here are a few examples of using the `docker image` command:

List all images:

    docker image ls

Pull an image from a registry:

    docker image pull ubuntu

Build an image from a Dockerfile:

    docker image build -t my-image .

Display detailed information about an image:

    docker image inspect my-image

Save an image to a tar archive:

    docker image save my-image > my-image.tar

Load an image from a tar archive:

    docker image load < my-image.tar

Remove an image:

    docker image rm my-image

## docker container command

The `docker container` command is used to manage Docker containers.
    
    docker container COMMAND

It has the following options or parameters:

-   `attach`: Attach local standard input, output, and error streams to a running container.
-   `commit`: Create a new image from a container's changes.
-   `cp`: Copy files or directories between a container and the local filesystem.
-   `create`: Create a new container.
-   `exec`: Run a command in a running container.
-   `export`: Export a container's filesystem as a tar archive.
-   `inspect`: Display detailed information on one or more containers.
-   `kill`: Kill one or more running containers.
-   `logs`: Fetch the logs of a container.
-   `ls`: List containers.
-   `pause`: Pause all processes within one or more containers.
-   `port`: List port mappings or a specific mapping for the container.
-   `prune`: Remove all stopped containers.
-   `rename`: Rename a container.
-   `restart`: Restart one or more containers.
-   `rm`: Remove one or more containers.
-   `run`: Run a command in a new container.
-   `start`: Start one or more stopped containers.
-   `stats`: Display a live stream of container(s) resource usage statistics.
-   `stop`: Stop one or more running containers.
-   `top`: Display the running processes of a container.
-   `unpause`: Unpause all processes within one or more containers.
-   `update`: Update configuration of one or more containers.
-   `wait`: Block until one or more containers stop, then print their exit codes.

Each subcommand has its own set of options and parameters. You can use the `docker container <subcommand> --help` command to see the options and parameters for a specific subcommand.

Here are a few examples of using the `docker container` command:

List all containers:

    docker container ls

Run a command in a new container:

    docker container run -it --name my-container ubuntu bash

Start a stopped container:

    docker container start my-container

Stop a running container:

    docker container stop my-container

Remove a container:

    docker container rm my-container

Fetch the logs of a container:

    docker container logs my-container

Display detailed information about a container:

    docker container inspect my-container

Execute a command in a running container:

    docker container exec my-container ls /

## docker exec command

The `docker exec` command is used to run a command in a running container. 

    docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

It has the following options or parameters:

-   `--detach` or `-d`: Run the command in the background.
-   `--detach-keys`: Override the key sequence for detaching a container.
-   `--env`: Set environment variables.
-   `--interactive` or `-i`: Keep the standard input open even if not attached.
-   `--privileged`: Give extended privileges to the command.
-   `--tty` or `-t`: Allocate a pseudo-TTY.
-   `--user`: Set the username or UID for the command.
-   `--workdir`: Set the working directory inside the container.

To run a command in a container, you need to provide the container ID or name as the first argument, followed by the command and its arguments.

Here are a few examples of using the `docker exec` command:

Execute a command in a running container:

    docker exec my-container ls /

Run a command in a running container and keep the standard input open:

    docker exec -i my-container bash

Run a command in a running container with extended privileges:

    docker exec --privileged my-container apt update

Run a command in a running container as a specific user:

    docker exec --user 1000:1000 my-container ls /home

Set an environment variable and run a command in a running container:

    docker exec --env FOO=bar my-container env

## docker build command

The `docker build` command is used to build an image from a Dockerfile.
   
    docker build [OPTIONS] PATH | URL | -

It has the following options or parameters:

-   `-t, --tag`: Add a custom tag to the image in the `name:tag` format.
-   `--file`: Specify the path to the Dockerfile. If not specified, the default is `./Dockerfile`.
-   `--build-arg`: Set a build-time variable in the form `name=value`. These variables can be used in the Dockerfile using the `ARG` instruction.
-   `--cache-from`: A list of image names or image digests to consider as cache sources when building the image.
-   `--no-cache`: Do not use the cache when building the image.
-   `--force-rm`: Remove intermediate containers after a successful build.
-   `--rm`: Remove intermediate containers after the build, even if an error occurs.

You can also specify the path to the directory containing the Dockerfile as the `PATH` argument, or you can specify a URL to a Git repository as the `URL` argument.

Here are a few examples of using the `docker build` command:

Build an image from a Dockerfile located in the current directory and tag it as `myimage`:

    docker build -t myimage .` 

Build an image from a Dockerfile located in a specific directory and tag it as `myimage`:

    docker build -t myimage /path/to/directory` 

Build an image from a Dockerfile located in a Git repository and tag it as `myimage`:    

    docker build -t myimage https://github.com/user/repo.git` 

Build an image from a Dockerfile located in a Git repository, specifying a particular branch and tag it as `myimage`:

    docker build -t myimage https://github.com/user/repo.git#branch` 

Build an image from a Dockerfile located in a Git repository and specify a custom Dockerfile name:

    docker build --file /path/to/custom/Dockerfile -t myimage https://github.com/user/repo.git` 

Build an image from a Dockerfile and set a build-time variable:

    docker build --build-arg VARNAME=value -t myimage .` 

Build an image from a Dockerfile and use a specific image as a cache source:

    docker build --cache-from image:tag -t myimage .` 

Build an image from a Dockerfile and disable the cache:

    docker build --no-cache -t myimage .` 

Build an image from a Dockerfile and remove intermediate containers after a successful build:

    docker build --force-rm -t myimage .` 

Build an image from a Dockerfile and remove intermediate containers after the build, even if an error occurs:

    docker build --rm -t myimage .` 

Build an image from a Dockerfile in the current directory:

    docker build .

Build an image from a Dockerfile in a specific directory:

    docker build /path/to/my-app

Build an image from a Dockerfile hosted on a remote server:

    docker build https://example.com/my-app.git

Build an image from a Dockerfile and specify a custom image name and tag:

    docker build -t my-image:latest .

Build an image from a Dockerfile and specify build arguments:

    docker build --build-arg arg1=value1 --build-arg arg2=value2 .

Build an image from a Dockerfile and specify a target stage to build:

    docker build --target my-stage .

Build an image from a Dockerfile and use specific images as cache sources:

    docker build --cache-from image1:tag1 --cache-from image2:tag2 .

Build an image from a Dockerfile and suppress the build output:

    docker build -q .

## docker logs command

The `docker logs` command is used to fetch the logs of a container. 

    docker logs [OPTIONS] CONTAINER

It has the following options or parameters:

-   `--details`: Show extra details provided to logs.
-   `--follow` or `-f`: Follow log output.
-   `--since`: Show logs since a specific timestamp or relative time.
-   `--tail`: Show a specific number of lines from the end of the logs.
-   `--timestamps` or `-t`: Show timestamps.

To fetch the logs of a container, you need to provide the container ID or name as an argument to the `docker logs` command.

Here are a few examples of using the `docker logs` command:

Fetch the logs of a container:

    docker logs my-container

Follow the log output of a container:

    docker logs -f my-container

Show logs since a specific timestamp:

    docker logs --since "2022-01-01T12:00:00" my-container

Show logs since a relative time:

    docker logs --since "1h" my-container

Show a specific number of lines from the end of the logs:

    docker logs --tail 100 my-container

Show timestamps in the logs:

    docker logs -t my-container

## docker pull command

The `docker pull` command is used to pull an image or a repository from a registry.

    docker pull [OPTIONS] NAME[:TAG|@DIGEST]

It has the following options or parameters:

-   `--all-tags` or `-a`: Download all tagged images in the repository.
-   `--disable-content-trust`: Skip image signing.
-   `--platform`: Set the platform if the registry is multi-platform capable.

To pull an image or a repository from a registry, you need to provide the name and optionally the tag or digest of the image as an argument to the `docker pull` command. The name of the image is usually in the form `registry/namespace/repository`.

Here are a few examples of using the `docker pull` command:

Pull an image from a registry:

    docker pull ubuntu:20.04

Pull all tagged images in a repository:

    docker pull -a my-image

Pull an image from a private registry:

    docker pull registry.example.com/my-image:latest

Pull an image from a specific platform:

    docker pull --platform linux/arm64 my-image:latest

## docker push command

The `docker push` command is used to push an image or a repository to a registry.

    docker push [OPTIONS] NAME[:TAG]

It has the following options or parameters:

-   `--disable-content-trust`: Skip image signing.

To push an image or a repository to a registry, you need to provide the name and optionally the tag of the image as an argument to the `docker push` command. The name of the image is usually in the form `registry/namespace/repository`.

Here are a few examples of using the `docker push` command:

Push an image to a registry:

    docker push my-image:latest

Push an image to a private registry:

    docker push registry.example.com/my-image:latest

Push an image with a specific tag:

    docker push my-image:1.0.0

