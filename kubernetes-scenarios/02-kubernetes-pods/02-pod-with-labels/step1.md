Let's create two Pods and use labels to select them.

Create pod1:

```yaml
cat <<EOF > pod1.yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod1
  labels:
    app: nginx
    environment: dev
    version: v1
spec:
  containers:
  - name: nginx
    image: reyanshkharga/nginx:v1
    ports:
    - containerPort: 80
EOF
```{{exec}}


Create pod2:

```yaml
cat <<EOF > pod2.yaml
apiVersion: v1
kind: Pod
metadata:
  name: pod2
  labels:
    app: nginx
    environment: prod
    version: v2
spec:
  containers:
  - name: nginx
    image: reyanshkharga/nginx:v2
    ports:
    - containerPort: 80
EOF
```{{exec}}
