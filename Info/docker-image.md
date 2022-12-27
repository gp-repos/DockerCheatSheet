# docker image command

The `docker image` command is used to manage Docker images.

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

### Here are a some examples of using the `docker image` command:

List images:

    docker image ls

Remove unused images:

    docker image prune

Pull an image from a registry:

    docker image pull ubuntu

Push an image to a registry:

    docker image push myimage

Remove an image:

    docker image rm myimage

Save an image to a tar archive:

    docker image save -o myimage.tar myimage

Tag an image:

    docker image tag myimage myimage:latest

Build an image from a Dockerfile located in the current directory and tag it as `myimage`:

    docker image build -t myimage .

Show the history of an image:

    docker image history myimage

Import an image from a tar archive:

    docker image import myimage.tar

Display detailed information about an image:

    docker image inspect myimage

Load an image from a tar archive:

    docker image load -i myimage.tar
