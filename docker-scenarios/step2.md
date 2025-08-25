Create a Docker image and run container.

Let's see how you can create your own Docker image based on your requirements. In this tutorial, we will create a customized version of the Nginx image that serves an HTML page we want.

> **Key Point:**  
> 1. By default, nginx serves the index.html file present in `/usr/share/nginx/html` directory. You can verify this by checking the content of `/etc/nginx/conf.d/default.conf`
> 2. We'll replace the default `index.html` with our `index.html` file.

<br>
```
<!DOCTYPE HTML>
<html>
    <head>
        <title>Nginx</title>
    </head>
    <body>
        <h2>Hello from Nginx container</h2>
    </body>
</html>
```{{exec}}


Next, let's cratea a pod:

```yaml
cat <<EOF > 01-basic.yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod-basic
spec:
  containers:
    - name: busybox
      image: busybox
      command: ["echo", "Hello from Pod!"]
EOF
```{{exec}}