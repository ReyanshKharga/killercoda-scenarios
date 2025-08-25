
> **Important Points:**
> 1. You can use `--detach` or `-d` option to run container in background.  
> 2. You can use `--name` option to assign a desired name to the container.  
<br>
Run a container in detached mode.

```
docker run -d --name my-nginx-container nginx:latest
```{{exec}}


Or run it in background:

```
docker run -d -p 80:80 nginx:alpine
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
