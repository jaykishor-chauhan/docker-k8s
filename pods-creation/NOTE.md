## Imperative Pod commands

Create a temporary Nginx Pod directly from the command line:

```powershell
kubectl run nginx-pod --image=nginx
kubectl get pods
kubectl get pods --watch
kubectl delete pod nginx-pod
```

Create a Pod with an exposed container port:

```powershell
kubectl run my-pod --image=nginx --port=80
```

## Declarative Pod manifest

Create the Pod defined in `pod.yml`:

```powershell
kubectl create -f pod.yml
kubectl get pod my-first-pod
kubectl describe pod my-first-pod
kubectl logs my-first-pod
kubectl edit pod my-first-pod
```

Inspect Kubernetes resource documentation:

```powershell
kubectl explain pod
```

## Inspect and generate Pod definitions

Open a shell inside the running container:

```powershell
kubectl exec -it my-first-pod -- sh
```

Show labels attached to a Pod:

```powershell
kubectl get pod my-first-pod --show-labels
```

Show the Pod IP and the node running it:

```powershell
kubectl get pod my-first-pod -o wide
```

List cluster nodes and their details:

```powershell
kubectl get node
kubectl get node -o wide
```

Show detailed Pod events, status, and configuration:

```powershell
kubectl describe pod my-first-pod
```

Generate a manifest without creating the Pod; for example, save an Nginx Pod as JSON:

```powershell
kubectl run nginx-pod --image=nginx:latest --dry-run=client -o json > ngnix-pod.json
```

Print the same generated manifest as YAML:

```powershell
kubectl run nginx-pod --image=nginx:latest --dry-run=client -o yaml
```

