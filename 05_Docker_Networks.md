# List docker networks
    
    alias docker='sudo docker'
    docker network COMMAND
    Docker network ls

# Create two new docket networks

    docker network create frontend
    docker network create backend

# Inspect the networks

    docker network inspect frontend
    docker network inspect backend

# Attach the networks to web01 container

    docker network connect frontend web01
    docker network connect backend web01
    docker network connect backend test2
    docker network inspect backend
    docker exec web01 apt-get update -y && docker exec web01 apt-get install iputils-ping -y
    docker exec web01 ping test2
    docker exec test2 apt-get install curl -y
    docker exec test2 curl web01

# Create a new container named db01 with backend network attached

    docker run -d -it --network frontend --name proxy1 ubuntu:14.04
    docker ps
    docker network inspect frontend
    docker network inspect proxy1