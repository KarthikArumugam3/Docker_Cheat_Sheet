# Docker cheat sheet
## A collection of all useful docker commands.

[![Docker](https://www.docker.com/wp-content/uploads/2022/03/Moby-logo.png)](https://www.docker.com)

### 1. Pulling and running a container:-
| Command                                                    | Description                |
|------------------------------------------------------------|----------------------------|
| `docker pull nginx`                                        | Pull Nginx                 |
| `docker run --name docker-nginx -p 80:80 nginx`            | Expose Nginx 80 Port       |
| `docker run --name docker-nginx -p 8080:80 -d nginx`       | Expose 8080 Port           |
| `docker run -P nginx`                                      | Randomly map ports         |
| `docker run -d -P nginx`                                   | Detached mode, random ports|
| `docker run --name test-ubuntu -it ubuntu:16.04 ./bin/bash`| Run Ubuntu interactively   |


### 2. Building and running a container from scratch using Dockerfile:-
| Command                                                    | Description                |
|------------------------------------------------------------|----------------------------|
| `docker build -t <container_name>:latest .`  | Create image using this directory's Dockerfile|
| `docker run -p 4000:80 <container_name>:latest`| Run the container, mapping port 4000 to 80|
|`docker run -d -p 4000:80 <container_name>:latest`| Run the container in detached mode, mapping port 4000 to 80|
|`docker exec -it <container_id> /bin/bash`| Enter inside a running container using **container_id**|

### 3. Managing Containers:-
| Command                          | Description                |
|----------------------------------|----------------------------|
| `docker ps`                      | See a list of all running containers |
| `docker ps -a`                   | See a list of all containers, even the ones not running |
| `docker stop <hash>`             | Gracefully stop the specified container |
| `docker start container_id`      | Start an already created container using the container id |
| `docker kill <hash>`             | Force shutdown of the specified container |
| `docker rm <hash>`               | Remove the specified container from this machine |
| `docker rm $(docker ps -a -q)`   | Remove all containers from this machine |
| `docker exec -it [container-id] /bin/bash` | Enter a running container |
| `docker logs <container-id> -f`  | Live tail a container's logs |
| `docker system prune`            | Remove all unused containers, networks, images (both dangling and unreferenced), and optionally, volumes. (Docker 17.06.1-ce and superior) |
| `docker system prune -a`         | Remove all unused containers, networks, images not just dangling ones (Docker 17.06.1-ce and superior) |
| `docker rm $(docker ps -aq)`     | Delete all stopped containers |


## 4. Managing Images:-
| Command                          | Description                |
|----------------------------------|----------------------------|
| `docker images -a`               | Show all images on this machine |
| `docker rmi <imagename>`         | Remove the specified image from this machine |
| `docker rmi -f <imagename>` | Forcefully remove the specified image from this machine |
| `docker rmi $(docker images -q)` | Remove all images from this machine |
| `docker rmi -f $(docker images -q)` | Delete all images |

### 5. Shipping a Docker container to a custom Docker Repository:-
| Command                                                    | Description                |
|------------------------------------------------------------|----------------------------|
| `docker login`  | Log in this CLI session using your Docker credentials Ex:- (Username, Password) |
| `docker tag <image_name> username/<repository_name>:tag` |  Tag <image_name> for upload to registry |
| `docker push username/<repository_name>:tag`  |  Upload tagged image to registry |
| `docker pull username/<repository_name>:tag`  |  Pull tagged image from registry |
| `docker run username/repository:tag`  | Run image from a registry |

### 6. Docker Volumes:-
| Command                          | Description                |
|----------------------------------|----------------------------|
| `docker volume create my_vol`    | Create a volume            |
| `docker volume ls`               | List volumes               |
| `docker volume inspect my_vol`   | Inspect a volume (troubleshooting) |
| `docker volume rm my_vol`        | Remove a volume            |
| `docker volume prune`            | Remove all unused local volumes |

### 7. Docker Networks:-
| Command                          | Description                |
|----------------------------------|----------------------------|
| `docker network prune`           | Remove all unused networks |














