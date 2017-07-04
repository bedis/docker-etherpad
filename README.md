# docker-etherpad
Etherpad over alpine Linux in a Docker container

[Etherpad](http://etherpad.org) is a highly customizable Open Source online editor providing collaborative editing in really real-time.

# Building the container

Clone this repository, go into the directory and run a command like: `docker build --tag etherpad --build-arg ETHERPAD_VER=1.6.1 .`

It is mandatory to precise a version number for gdns through the argument **ETHERPAD_VER**.

One can also use the docker-compose.yml file provided here: `docker-compose build`

# Using the container

## Normal usage

Use a command like this one:

  `docker run --detach --rm=true --volumes ./data/settings.json:/opt/etherpad/settings.json \\
              --volumes ./data/node_modules:/opt/etherpad/node_modules --volumes ./data/var:/opt/etherpad/var \\
              --name=etherpad --hostname=etherpad etherpad`

Or use docker-compose:

  `docker-compose up -d`

## Debugging

Use a command like this one:

  `docker run --detach -it --rm=true --volumes ./data/settings.json:/opt/etherpad/settings.json \\
              --volumes ./data/node_modules:/opt/etherpad/node_modules --volumes ./data/var:/opt/etherpad/var \\
              --name=etherpad --hostname=etherpad --entrypoint=sh etherpad`

Or use docker-compose:

  `docker-compose up`

