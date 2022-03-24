# Docker_Practice

Docker Labs - Installing Docker ( My plan )

# Setup Vagrant environment and Install Docker

   1. Turn on Vagrant Instance

     vagrant up

   2. SSH connect node1 and setup local DNS, and test

     vagrant ssh node1
     sudo cp /vagrant/hosts_file /etc/hosts
     ping node1
     ping node2

   3. Install Docker

     sudo apt update -y && sudo apt-get install docker.io -y

# Two pieces of Docker. The client and the server, they are decoupled.

   4. Verify Installation

    sudo docker version
    sudo docker info

   5. Setup Aliases
        
     alias docker='sudo docker'
     alias d='docker'
     alias stopdocks='docker stop $(docker ps -a -q)'
     alias rmdocks='docker rm $(docker ps -a -q)'

# Download our First Image

   6. Check to see current images, by default there is none

     docker images

   7. Pull the image 'ubuntu:14.04'

     docker pull ubuntu:14.04

   8. See that the image now exists

     docker images

# Run our first container

   9. See that no docker containers are running

     docker ps -a

   10. Start a container

     docker run -it ubuntu:14.04
  # Now exit container
     exit
 # Container stopped
     docker ps -a

   11. Start a container in detached mode

     docker run -d -it ubuntu:14.04
     docker ps
     docker attach <container id>