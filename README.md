# gitops-tests

## Prerequisite

This setup assumes you have a local cluster rready to be used.

## Deployment

To deploy ArgoCD with this test setup, you need to configure the correct clusters.
We try to simultate multiple clusters using different namespaces and cluster names, all present on the `in-cluster`.

First, update the cluster configuration file `private.yaml` at `./services/argo-cd/base/clusters`. You can use
the values from your `~/.kube/config` file.

Then, deploy argocd to your local cluster

```bash
kubectl apply -n argocd -k ./services/argo-cd
```

## Bootstrap

At first, the [sync-projects](./bootstrap/sync/sync-projects.yaml) application must be applied manually.

Then, the [bootstrap](./bootstrap/sync/bootstrap.yaml) can be applied manually.

```bash
kubectl apply -n argocd -f bootstrap/sync/sync-projects.yaml
kubectl apply -n argocd -f bootstrap/sync/bootstrap.yaml
```
