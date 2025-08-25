Run Docker container from a public Docker image.

> **Key Points:**  
> 1. Use `--detach` or `-d` to run a container in the background.  
> 2. Use `--name` to assign a custom name to the container.  
> 3. Use `-p` to map a container port to a host port.
<br>

Run a container in detached mode.

```
docker run -d --name my-nginx-container -p 80:80 nginx:latest
```{{exec}}

Now access Nginx using this link:

[ACCESS NGINX]({{TRAFFIC_HOST1_80}})

It's also possible to access ports using the top-right navigation in the terminal.
Or we can display the link to that page:

[ACCESS PORTS]({{TRAFFIC_SELECTOR}})

It's also possible to generate access URLs in bash (foreground or background scripts) like this:

```
sed 's/PORT/80/g' /etc/killercoda/host
```{{exec}}
