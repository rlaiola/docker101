# create swarm
docker swarm init

# deploy stack
docker stack deploy --compose-file ../compose/docker-compose.yml -c docker-swarm.yml boca-stack

# list services
docker service ls

# visit http://localhost:8000/boca to check
# whether the service is up and running

# scale a single service
docker service scale boca-stack_boca-jail=4

# bring stack down
docker stack rm boca-stack

# leave swarm
docker swarm leave --force
