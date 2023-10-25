| Command | Description |
|----|----|
| docker build -t _name_ . | creates an image called _name_ from the specified .Dockerfile |
| docker pull <em>image</em> | pulls an image from Dockerhub |
| docker images | shows all the images in our machine |
| docker ps | shows all the running containers |
| docker ps -a | shows all the containers including stopped containers |
| docker run <em>image</em> | creates a container from an image |
| docker stop <em>container_id / container_name</em> | stops a running container |
| docker system prune -f | To remove all stopped containers (docker do not touch the running containers) |
| docker system prune -a | To remove all stopped containers (docker do not touch the running containers) + unused images |
| docker rm _id_ | Removes container |
| docker network create _network-name_ | Creates a network containers can communicate with |
|  |  |

