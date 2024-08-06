## alpine images are smaller
docker run postgres:alpine

## docker run command - (create and start a container)
- docker run is equivalent to `docker create` + `docker start`

docker run \<image-name> \<command>

docker run -it redis

docker run hello-world

docker run busybox echo hi there

docker run -it busybox sh
 - run with shell


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

## create containers
docker create hello-world 

docker create busybox echo hello
- echo hello is the default command for the container, this command cannot be changed later



## start container
docker start \<container-id>

docker start 78bfb518b2b5031f885696ae1932156752c71fdca6f20c4d40a4af2b21ce5238

docker start -a 78bfb518b2b5031f885696ae1932156752c71fdca6f20c4d40a4af2b21ce5238
- a is for attach to the output of process and print it in the terminal

## removing stopped containers
docker system prune 
- this will remove all stopped containers
- networks and dangling images
- and all build cache

## get ouptput of container
docker logs [container-id]

docker logs 247d3cc26ecb

## stop container
docker stop [container-id]
- SIGTERM message sent to process
- will wait 10 seconds for process to stop, if not stopped, kill signal is sent 

docker stop 247d3cc26ecb

## kill container
docker kill [container-id]
- SIGKILL is sent, process killed abruptly

docker kill 247d3cc26ecb

## run command in a running container
docker exec -it [container-id] [command]
- -it is used to connected to stdin/stdout/stderr

docker exec -it bf2adc3b852b redis-cli

## get shell access to running container
docker exec -it [container-id] sh

docker exec -it bf2adc3b852b sh


## build image
docker build .

docker build -t myredis/redis:latest .
- -t is to tag the built image, [your-id]/[base-image]:[version] is the convention to tag images


## create image from a running container
docker commit -c "CMD 'redis-server'" CONTAINERID
- for linux users

docker commit -c 'CMD ["redis-server"]' CONTAINERID
- for windows users

## Sample docker file
```Dockerfile

FROM node:alpine

COPY ./ ./

RUN npm i express

CMD ["npm", "start"]

```
## build and run the above docker file
docker build -t node-app .

docker run -p 8080:8080 node-app

