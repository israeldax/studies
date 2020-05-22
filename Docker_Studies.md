# Docker Studies

## [Docker Machine](https://docs.docker.com/machine/overview/)

**Tool for manage a dockerized host**. It has its own command line client and the docker client. It is possible to use docker-machine to install the docker engine in virtual systems (locally or remote).

#### Important Commands

- docker-machine ls
- docker-machine active
- docker-machine ip
- docker-machine env
- docker-machine start/stop

## Images

#### Important Commands

- docker image pull \<image>:\<tag>
  > Download image
- docker image ls
- docker image rm

## Containers

#### Important Commands

- docker container ls
- docker container run \<container>
  > This command will download the image if it doesn`t exist.
  - -it \<container> _[sh]_ (Turns on iteractive terminal and access it through shell)
    - \<ctrl + d> (Quit shell)
    - \<ctrl + p> + \<ctrl + q> (Leave it running in the background. Can only be ran with the -it option)
  - -d \<container> (Run in detach mode)
  - -p \<your port>:\<container port> (Set port)
  - -v \<your path>:\<container path> (Set a volume)
  - --name \<name> (to name a container)
  - --network \<network name> (Set a network for the container)
  - --rm \<container> (run container and remove it)
    > Run a container and deletes it
- docker container attach \<container>
  - docker container exec -it \<container> bash
- docker container start/stop \<container>
- docker container rm \<container>
- docker container rm \$(docker container ls -aq)
- docker container prune (delete all stopped containers)
- docker container exec \<container> \<command>
  > To execute a command in the container
- docker container logs [-f] \<container>

## Network

Containers run in isolation by using a feature of the linux kernel called _namespaces_. We can make them comunicate by a network. If you don`t explicity set the network it will default to the **bridge** network. In this case you may use the --link option, but it is deprecated.

#### Important Commands

- docker network ls
- docker network create \<network name>

## Dockerfile

An image is created based on a dockerfile.

#### Important Commands

- docker image build -t \<image name>:\<tag name> \<path to Dockerfile>
- docker image tag \<image>:\<tag> \<user name>/\<new name>:\<new tag>

  > Rename a docker image

  > To push an image it must be namespaced with your docker id

- docker image pull \<user name>/\<new name>:\<new tag>

#### Keywords

- \# (Comments)
- FROM \<image> (On wich image our image will be based on)
- RUN \<command> (A command that will run in the context of the image)
- CMD \<command> (A command that will run when the container starts)
  > Better use _(json)_ exec format ["bin", "opt", "opt"] otherwise the default
  > shell format will not forward interupt to the container.

## General

#### Important Commands

- docker login
- docker version
- hostname
- cat /etc/os-release
