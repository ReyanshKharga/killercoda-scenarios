Run Docker container from a public Docker image.

> **Key Points:**  
> 1. Use `--detach` or `-d` to run a container in the background.  
> 2. Use `--name` to assign a custom name to the container.  
> 3. Use `-p` to map a container port to a host port.


**Step 1: Run nginx container in detached mode:**

```
docker run -d --name my-nginx-container -p 80:80 nginx:latest
```{{exec}}
<br>


**Step 2: List running containers:**

```
docker ps
```{{exec}}
<br>


**Step 3: View Container Logs**

```
docker logs -f my-nginx-container
```{{exec}}
<br>


**Step 4: Exit

```
^c
```{{exec}}
<br>


**Step 5: Start a shell session inside the container:**

```
docker exec -it my-nginx-container bash
```{{exec}}
<br>


**Step 6: Access the localhost endpoint:**

```
curl localhost
```{{exec}}
<br>


**Step 7: Exit from the container:**

```
exit
```{{exec}}
<br>


**Step 8: Stop the container:**

```
docker stop my-nginx-container
```{{exec}}
<br>


**Step 9: List all containers and verify if the container is stopped:**

```
docker ps -a
```{{exec}}
<br>


**Step 10: Start the container:**

```
docker start my-nginx-container
```{{exec}}
<br>


**Step 11: List all containers and verify if the container is started:**

```
docker ps -a
```{{exec}}
<br>


**Step 12: Stop and delete the container:**

```
docker stop my-nginx-container
docker rm my-nginx-container
```{{exec}}