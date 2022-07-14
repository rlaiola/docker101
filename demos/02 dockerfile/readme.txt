# pull and run official ubuntu image
docker pull ubuntu:18.04
docker image ls -a
docker run --name test1 -it ubuntu:18.04

# check whether vim is installed

# other useful commands
docker container ls -a
docker start test1
docker exec -it test1 /bin/bash

# create new image
docker build . -t myubuntu

# stop and remove container
docker stop test1
docker rm test1
