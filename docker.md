## alpine images are smaller
docker run postgres:alpine

## docker run command
- docker run is equivalent to `docker create` + `docker start`

docker run \<image-name> \<command>

docker run -it redis

docker run hello-world

docker run busybox echo hi there

## run with params
docker run --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres -p 5432:5432

- --name name of container
- -e environment variable
- -d run in detached mode
- -p host_port:container_port

## list containers
docker ps

## list all created containers (both shutdown and running)
docker ps --all

## list iamges
docker images
