# Docker Images / current Images

    docker images
  
# Download docker images, and list images

    docker pull ubuntu:latest
    docker search nginx
    docker pull nginx:latest
    docker images 
   
# Create a container, install python, commit the image

    docker run -it ubuntu:14.04
    apt-get update -y && apt-get install python -y
    python
    print("hello world")
    exit()

# Open new Shell

    vagrant ssh node1    
    alias docker='sudo docker'
    sudo docker ps -a
    sudo docker commit <container id> ubuntu:python 

# See images

    docker images
    docker history ubuntu:python

# Create a container with your new image

    docker run -it ubuntu:python