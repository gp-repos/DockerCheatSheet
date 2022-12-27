# docker build command

The `docker build` command is used to build an image from a Dockerfile.
   
    docker build [OPTIONS] PATH | URL | -

Here are some commonly used optional parameters of `docker run` command:

-   `-t, --tag`: Add a custom tag to the image in the `name:tag` format.
-   `--file`: Specify the path to the Dockerfile. If not specified, the default is `./Dockerfile`.
-   `--build-arg`: Set a build-time variable in the form `name=value`. These variables can be used in the Dockerfile using the `ARG` instruction.
-   `--cache-from`: A list of image names or image digests to consider as cache sources when building the image.
-   `--no-cache`: Do not use the cache when building the image.
-   `--force-rm`: Remove intermediate containers after a successful build.
-   `--rm`: Remove intermediate containers after the build, even if an error occurs.

You can also specify the path to the directory containing the Dockerfile as the `PATH` argument, or you can specify a URL to a Git repository as the `URL` argument.

### Here are a some examples of using the `docker build` command:

Build an image from a Dockerfile in the current directory:

    docker build .

Build an image from a Dockerfile and specify a custom image name and tag:

    docker build -t my-image:latest .
    
Build an image from a Dockerfile in a specific directory:

    docker build /path/to/my-app

Build an image from a Dockerfile located in a specific directory and tag it as `myimage`:

    docker build -t myimage /path/to/directory

Build an image from a Dockerfile located in a Git repository and tag it as `myimage`:    

    docker build -t myimage https://github.com/user/repo.git

Build an image from a Dockerfile located in a Git repository, specifying a particular branch and tag it as `myimage`:

    docker build -t myimage https://github.com/user/repo.git#branch

Build an image from a Dockerfile located in a Git repository and specify a custom Dockerfile name:

    docker build --file /path/to/custom/Dockerfile -t myimage https://github.com/user/repo.git

Build an image from a Dockerfile and set a build-time variable:

    docker build --build-arg VARNAME=value -t myimage .
    
Build an image from a Dockerfile and specify build arguments:

    docker build --build-arg arg1=value1 --build-arg arg2=value2 .
    
Build an image from a Dockerfile and use a specific image as a cache source:

    docker build --cache-from image:tag -t myimage .

Build an image from a Dockerfile and use specific images as cache sources:

    docker build --cache-from image1:tag1 --cache-from image2:tag2 .
    
Build an image from a Dockerfile and disable the cache:

    docker build --no-cache -t myimage .

Build an image from a Dockerfile and remove intermediate containers after a successful build:

    docker build --force-rm -t myimage .

Build an image from a Dockerfile and remove intermediate containers after the build, even if an error occurs:

    docker build --rm -t myimage .

Build an image from a Dockerfile and specify a target stage to build:

    docker build --target my-stage .

Build an image from a Dockerfile and suppress the build output:

    docker build -q .
