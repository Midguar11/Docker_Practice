# List docker networks

    sudo docker swarm init sudo docker swarm init --advertise-addr 192.168.56.180

# Open new shell
    vagrant ssh node2
    docker swarm join --token SWMTKN-1-44ropyzqiq02rytzgw0fx1ieaoj98vf2u4mg7l6di122ezufp7-bz1omf6j0zu76rm3v0ngszemr 192.168.56.180:2377
    alias docker='sudo docker'
  
  # Back to Node1 shell

    alias docker='sudo docker'
    docker node ls
    docker node ps
    docker node inspect self

    docker service create --replicas 1 --name pingdocker ubuntu:14.04 ping docker.com
    docker service scale pingdocker=5
    docker service ls
    docker node ps node2
    docker node ps node1