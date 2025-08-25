Create a Docker image and run container.

Let's see how you can create your own Docker image based on your requirements. In this tutorial, we will create a customized version of the Nginx image that serves an HTML page we want.

> **Key Point:**  
> 1. By default, nginx serves the index.html file present in `/usr/share/nginx/html` directory. You can verify this by checking the content of `/etc/nginx/conf.d/default.conf`
> 2. We'll replace the default `index.html` with our `index.html` file.

<br>
```html
cat <<EOF > index.html
&lt;!doctype html&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;title&gt;Nginx&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h2&gt;Hello from Nginx container1&lt;/h2&gt;
  &lt;/body&gt;
&lt;/html&gt;
EOF
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