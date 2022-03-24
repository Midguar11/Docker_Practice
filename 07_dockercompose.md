
# List docker networks

     alias docker-compose='sudo docker-compose'
     alias dc='sudo docker-compose'     
     apt-get install docker-compose -y
     dc version

     docker-compose up -d
     docker-compose ps
     docker-compose images



     docker-compose down
     docker-compose up -d --scale db=2
     docker-compose scale redis=4