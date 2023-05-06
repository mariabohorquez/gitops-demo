# gitops-demo
Demo for Applications Arquitecture Class

## Commands

### Setting up aws connection

```bash
# these are in the aws details in the lab
aws configure
aws configure set aws_session_token <token>
# verify connectivity with:
aws sts get-caller-identity
```

### Getting the lab to work

```bash
# Have docker running in the background
# Start minikube
minukube start
# Check argocd status
kubectl get all -n argocd
# Forward port
# Enter localhost:3000. Combo is admin / Hce1t8O1NsDNTXrZ
kubectl port-forward svc/argocd-server -n argocd 3000:443
```

### Tutorials used as reference

https://faun.pub/how-to-deploy-to-kubernetes-using-argo-cd-ee743cd3661b
https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/


