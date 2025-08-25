Run Docker container from a public Docker image.

> **Key Points:**  
> 1. Use `--detach` or `-d` to run a container in the background.  
> 2. Use `--name` to assign a custom name to the container.  
> 3. Use `-p` to map a container port to a host port.


<br>
Run nginx container in detached mode:

```
docker run -d --name my-nginx-container -p 80:80 nginx:latest
```{{exec}}


<br>
List running containers:

```
docker ps
```{{exec}}


<br>
Start a shell session inside the container:

```
docker exec -it my-nginx-container bash
```{{exec}}


<br>
Access the localhost endpoint:

```
curl localhost
```{{exec}}


<br>
Stop the container:

```
docker stop my-nginx-container
```{{exec}}


<br>
List all containers and verify if the container is stopped:

```
docker ps -a
```{{exec}}


<br>
Start the container:

```
docker start my-nginx-container
```{{exec}}


<br>
List all containers and verify if the container is started:

```
docker ps -a
```{{exec}}

<br>
Stop and delete the container:

```
docker stop my-nginx-container
docker rm my-nginx-container
```{{exec}}