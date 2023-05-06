# gitops-demo
Demo for Applications Arquitecture Class

## Commands

### Setting up aws connection (if you are running the lab via AWS)

```bash
# these are in the aws details in the lab
aws configure
aws configure set aws_session_token <token>
# verify connectivity with:
aws sts get-caller-identity
```

### Getting the lab to work with Minikube (local k8s engine)

```bash
# Have docker running in the background
# Start minikube
minukube start
# Check argocd status (before this be sure to follow a tutorial to setup argocd for the first time)
kubectl get all -n argocd
# Foward port and enter localhost:3000. Combo is admin / Hce1t8O1NsDNTXrZ
kubectl port-forward svc/argocd-server -n argocd 3000:443

# Get the deployment running by applying the files
kubectl apply -f deployment/
# Then get minikube to connect to the service
minikube service web
```


## Tutorials used as reference

https://faun.pub/how-to-deploy-to-kubernetes-using-argo-cd-ee743cd3661b
https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/
https://www.unixarena.com/2019/05/kubernetes-minikube-how-to-deploy-application-using-dashboard.html/
https://medium.com/@mehmetodabashi/installing-argocd-on-minikube-and-deploying-a-test-application-caa68ec55fbf
