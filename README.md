# GitOps-prod
- Create a submodule to the private repository
- Set up argo-cd to connect the private repo in "settings"
- Add kubernetes secret on the defualt and argocd namespace with the personal access token of private repository


- How to update the submodule

  `git submodule update --init
   cd value
   git checkout master
   cd ..
   git add value
   git commit -m "Update value submodule`


-  AWS EBS CSI Driver (to attach Elastic block storage to pods in k8s with storage classes, pv and pvc)
   `kubectl apply -k "github.com/kubernetes-sigs/aws-ebs-csi-driver/deploy/kubernetes/overlays/stable/?ref=release-1.16"`


-  Ingress Nginx controller for k8s cluster
   `helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
    helm repo update
    helm install nginx-ingress ingress-nginx/ingress-nginx --set controller.publishService.enabled=true`
