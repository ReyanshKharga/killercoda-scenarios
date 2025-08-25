**Step 1: Create a Pod using imperative approach:**

```
kubectl run my-pod --image=nginx
```{{exec}}
<br>


**Step 2: List Pods:**

```
kubectl get pods
```{{exec}}
<br>


**Step 3: List Pods with wide output:**

```
kubectl get pods -o wide
```{{exec}}
<br>


**Step 4: Describe the Pod:**

```
kubectl describe pod my-pod
```{{exec}}
<br>


**Step 5: Start a shell session inside the container:**

```
kubectl exec -it my-pod -- bash
```{{exec}}
<br>


**Step 5: Run commands:**

1. List files and folders:
```
ls
```{{exec}}
<br>

2. Access nginx running on port 80:
```
curl localhost
```{{exec}}
<br>


**Step 6: View container logs:**

```
kubectl logs my-pod
```{{exec}}
<br>


**Step 6: Delete Pod:**

```
kubectl delete pod my-pod
```{{exec}}
<br>