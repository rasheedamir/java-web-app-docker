# docker

## Docker in Brief

The docker project offers higher-level tools, working together, which are built on top of some Linux kernel features. The goal is to help developers and system administrators port applications - with all of their dependencies conjointly - and get them running across systems and machines - headache free.

Docker achieves this by creating safe, LXC (i.e. Linux Containers) based environments for applications called docker containers. These containers are created using docker images, which can be built either by executing commands manually or automatically through Dockerfiles.

## What Are Dockerfiles?

Dockerfiles are scripts containing commands declared successively which are to be executed, in the order given, by docker to automatically create a new docker image. They help greatly with deployments.

These files always begin with the definition of a base image by using the FROM command. From there on, the build process starts and each following action taken forms the final with commits (saving the image state) on the host.

## Creating the Docker Image for jhipster Containers

We can now create our first jhipster image by following the usage instructions explained in the Dockerfile Basics section.

Run the following command to create an image, tagged as `jhipster_img`:

`sudo docker build -t jhipster_img .`

Note: Do not forget the trailing `.` for docker to find the Dockerfile.

## Running dockerised jhipster Containers
t is very simple to create any number of perfectly isolated and self-contained jhipster instances - now - thanks to the image we have obtained in the previous section. All we have to do is to create a new container with `docker run`.

To create a new container, use the following command, modifying it to suit your requirements following this example:

# Example: `sudo docker run -name [container name] -p [port to access:port exposed] -i -t [jhipster image name]`
`sudo docker run -name jhipster_ins -d --p 8080:8080 -p 9000:9000 -p 35729:35729 -p 4022:22 jhipster_img`

Now we will have a docker container named `jhipster_ins`, accessible from ports 8080, 9000 run using our image tagged `jhipster_img`, which we built previously.