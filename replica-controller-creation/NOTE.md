# ReplicaSet Commands

```powershell
kubectl scale rs/nginx-rs --replicas=10
```

Scale

```text
replicaset.apps/nginx-rs scaled
```

```powershell
kubectl explain rc
```

Explain

Displays information about the ReplicaController resource, including its API version and kind.

```yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata: {name: nginx-rs, labels: {env: demo}}
spec: {replicas: 6, selector: {matchLabels: {env: demo}}, template: {metadata: {name: my-first-pod, labels: {env: demo, type: frontend}}, spec: {containers: [{name: my-first-pod-containers, image: nginx:latest, ports: [{containerPort: 80}]}]}}
```

```powershell
kubectl set image deploy/nginx-deploy my-first-pod-containers=nginx:1.9.1
```

Update

```text
deployment.apps/nginx-deploy image updated
```

```powershell
kubectl rollout undo deploy/nginx-deploy
```

Rollback

```powershell
kubectl create deployment deploy-nginx --image=nginx --dry-run=client -o yaml > deploy.yaml
kubectl create deployment deploy-nginx --image=nginx --dry-run=client -o json > deploy.json
```

Generate
