# Create dockerfile

     alias docker='sudo docker'   
     docker image build -t ubuntu:flask .
     docker image ls
     docker run -d --hostname webserv1 --name webserv1 -p 80:5000 ubuntu:flask
     docker exec webserv1 ps
     curl localhost