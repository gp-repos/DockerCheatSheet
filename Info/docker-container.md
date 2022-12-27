# docker container command

The `docker container` command is used to manage Docker containers.
    
    docker container COMMAND

Here are some commonly used optional parameters of `docker container` command:

-   `create`: Create a new container.
-   `run`: Run a command in a new container.
-   `start`: Start one or more stopped containers.
-   `stop`: Stop one or more running containers.
-   `restart`: Restart one or more containers.
-   `pause`: Pause one or more containers.
-   `unpause`: Unpause one or more paused containers.
-   `kill`: Kill one or more running containers.
-   `rm`: Remove one or more containers.
-   `inspect`: Display detailed information about a container.

### Here are a some examples of using the `docker container` command:

Start a stopped container:

    docker container start my-container

Stop a running container:

    docker container stop my-container
        
Create a new container based on the `nginx` image and run it in the background:

    docker container run -d --name mynginx nginx
    
Run a command in a new container:

    docker container run -it --name my-container ubuntu bash
    
List all containers:

    docker container ls
    
Restart a container:

    docker container restart mynginx

Pause a running container:

    docker container pause mynginx

Unpause a paused container:

    docker container unpause mynginx

Kill a running container:

    docker container kill mynginx

Remove a container:

    docker container rm my-container

Display detailed information about a container:

    docker container inspect my-container
    
Fetch the logs of a container:

    docker container logs my-container

Execute a command in a running container:

    docker container exec my-container ls /
    
### Complete list of optional parameters of `docker container` command:

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
