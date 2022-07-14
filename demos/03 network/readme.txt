# list existing networks
docker network ls

# create custom network
docker network create \
    --driver bridge \
    --subnet 182.18.0.0/16 \
    backend

# container database
docker run --name boca-db \
           --network backend \
           -e POSTGRES_USER=bocauser \
           -e POSTGRES_PASSWORD=dAm0HAiC \
           -d postgres:10

# container web app
docker run --name boca-web \
           --network backend \
           -p 8000:80 \
           -e DB_HOST=boca-db \
           -e DB_USER=bocauser \
           -e DB_NAME=bocadb \
           -e DB_PASSWORD=dAm0HAiC \
           -d ghcr.io/joaofazolo/boca-docker/boca-web

# show containers attached to network
docker network inspect backend

# visit http://localhost:8000/boca to check
# whether the service is up and running

# stop and remove containers
docker stop boca-db boca-web
docker rm boca-db boca-web

# remove custom network
docker network rm backend
