
# Inspect one of your containers

    docker inspect web01
    docker inspect web01 >> web01.json

# Add a filter to check some settings

    docker inspect -f '{{.Config.Image}}' web01
    docker inspect -f '{{.Config.Env}}' web01
    docker inspect -f '{{.Config.Hostname}}' web01
    docker inspect -f '{{.Mounts}}' test2
    docker inspect -f '{{.State.Pid}}' test2

# Advanced filter to loop through interfaces and reveal IP address

    docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' web01