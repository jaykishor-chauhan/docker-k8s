# Kind Kubernetes Cluster Notes

These commands create and inspect a local Kubernetes cluster with [Kind](https://kind.sigs.k8s.io/).

## Create the cluster

Run these commands from the `k8s` directory:

```powershell
.\kind create cluster --name docker-k8s --config config.yml
kubectl cluster-info
kubectl cluster-info --context kind-docker-k8s
```

The `config.yml` file creates one control-plane node and two worker nodes:

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
```

## Inspect nodes and pods

```powershell
kubectl get nodes
kubectl get node
kubectl get pods -A
```

## Manage Kubernetes contexts

```powershell
kubectl config get-contexts
kubectl config current-context
kubectl config use-context <context-name>
```

For this cluster, the context is usually `kind-docker-k8s`:

```powershell
kubectl config use-context kind-docker-k8s
```

