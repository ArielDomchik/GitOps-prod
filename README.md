# GitOps-prod
- Create a submodule to the private repository
- Set up argo-cd to connect the private repo in "settings"
- Add kubernetes secret on the defualt and argocd namespace with the personal access token of private repository


- How to update the submodule

 1. `git submodule update --init`
 2. `cd remote`
 3. `git checkout main`
 4. `cd ..`
 5. `git add remote`
 6. `git commit -m "Update remote submodule`


-  AWS EBS CSI Driver (to attach Elastic block storage to pods in k8s with storage classes, pv and pvc)
   `kubectl apply -k "github.com/kubernetes-sigs/aws-ebs-csi-driver/deploy/kubernetes/overlays/stable/?ref=release-1.16"`


-  Ingress Nginx controller for k8s cluster
  1. `helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx`
  2. `helm repo update`
  3. `helm install nginx-ingress ingress-nginx/ingress-nginx --set controller.publishService.enabled=true`
