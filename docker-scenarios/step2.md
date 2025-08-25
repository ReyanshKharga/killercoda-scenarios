Let's see how you can create your own Docker image based on your requirements. In this tutorial, we will create a customized version of the Nginx image that serves an HTML page we want.

> **Key Point:**  
> 1. By default, nginx serves the index.html file present in `/usr/share/nginx/html` directory. You can verify this by checking the content of `/etc/nginx/conf.d/default.conf`
> 2. We'll replace the default `index.html` with our `index.html` file.


**Step 1: Create HTML file to be served by Nginx:**

```yaml
cat <<EOF > index.html
<!doctype html>
<html>
    <head>
        <title>Nginx</title>
    </head>
    <body>
        <h2>Hello from Nginx container</h2>
    </body>
</html>
EOF
```{{exec}}
<br>


**Step 2: Create Dockerfile:**

```yaml
cat <<EOF > Dockerfile
FROM nginx:latest

COPY ./index.html /usr/share/nginx/html/index.html
EOF
```{{exec}}
<br>


**Step 3: Verify if the files are created:**

```
ls
```{{exec}}
<br>


**Step 4: Build the Image**

```
docker build -t my-nginx-image:v1 .
```{{exec}}
<br>


**Step 5: Run a container from the image:**

```
docker run -d --name my-nginx-container -p 81:80 my-nginx-image:v1
```{{exec}}
<br>


**Step 6: Start a shell session inside the container:**

```
docker exec -it my-nginx-container bash
```{{exec}}
<br>


**Step 7: Access the localhost endpoint:**

```
curl localhost
```{{exec}}
<br>


**Step 8: Stop and delete the container:**

```
docker stop my-nginx-container
docker rm my-nginx-container
```{{exec}}