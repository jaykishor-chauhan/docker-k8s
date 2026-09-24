# Delete

kind delete cluster --name my-first-cluster

# Create

kind create cluster --name k8s-cluster

# Configure

kind create cluster --config .\cluster.yaml --name k8s-cluster

# Inspect

kubectl get nodes -o wide

# Endpoints

kubectl get ep
kubectl get endpoints

# Configuration

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 30007
    hostPort: 3007
- role: worker
- role: worker
```

# Apply the NodePort service

kubectl apply -f nodeport.yaml

# Access the nginx service

curl.exe http://localhost:3007
