# Bootstrap

At first, the [sync-projects](./sync/sync-projects.yaml) application must be applied manually.

Then, the [bootstrap](./sync/bootstrap.yaml) can be applied manually.

```bash
kubectl apply -n argocd -f bootstrap/sync/sync-projects.yaml
kubectl apply -n argocd -f bootstrap/sync/bootstrap.yaml
```
