# list images
docker images
# or
docker image ls -a

# list containers
docker container ls -a

# pull and run official ubuntu image
docker pull ubuntu:18.04
docker run --name test1 -it ubuntu:18.04

# other useful commands
docker start test1
docker exec -it test1 /bin/bash
docker stats
docker logs test1

# stop and remove container
docker stop test1
docker rm test1
