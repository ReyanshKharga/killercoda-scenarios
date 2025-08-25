Create a Docker image and run container.

Let's see how you can create your own Docker image based on your requirements. In this tutorial, we will create a customized version of the Nginx image that serves an HTML page we want.

> **Key Point:**  
> By default, nginx serves the index.html file present in /usr/share/nginx/html directory. You can verify this by checking the content of /etc/nginx/conf.d/default.conf

> We'll replace the default index.html with our index.html file.

<br>
```html
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