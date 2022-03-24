# See that containers exit out when they have completed execution.

    alias docker='sudo docker'
    docker run ubuntu:14.04 ls -l
    docker run ubuntu:14.04 date
    docker run ubuntu:14.04 hostname
    docker run -d -it ubuntu:14.04 
    docker exec <container id> ps -aux
    docker exec <container id> kill 1
    docker start <container id> 

  
# Set an environment variable

    docker run -d -it --name test1 -e MYSQL_PASSWORD='SecurePassword' ubuntu:14.04 bash    
    docker exec test1 env
   
# Map a Volume to a container

    cd ~/
    cd ~/data
    sudo touch myfile.txt
    docker run -d -it --name test2 -v ~/data:/~/data ubuntu:14.04 bash
    docker exec test2 ls /~/data
    docker exec test2 cat /~/data/myfile.txt
    docker exec test2 rm /~/data/myfile.txt
    docker exec test2 ls /~/data

# Start a NGINX container that forwards host port 8000 to container port 80

    docker run -d --name web01 -h web01 -p 8000:80 nginx
    curl localhost:8000

# Managing containers

    docker restart web01
    docker stop web01

# notice that you can't get to the page anymore

    curl localhost:8000
    docker start web01
    docker top web01
    docker stats

# Using Docker Logs

    docker attach test
    ls -l
    exit
    docker logs test