# list existing networks
docker network ls

# create custom network
docker network create traefik-proxy

# check whether new network was created
docker network ls

# start portainer and traefik
docker-compose -f docker-compose.core.yml up -d

# visit http://portainer.localhost to check
# whether Portainer is up and running

# visit http://traefik.localhost to check
# wether Traefik is up and running

# deploy BOCA as stacks in different path prefixes

# stop portainer and traefik
docker-compose -f docker-compose.core.yml down
