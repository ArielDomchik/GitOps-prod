
# GitOps-prod

This repository is used to deploy the production version of the application using ArgoCD. The following steps have been taken to set up this repository:

-   A submodule called "remote" has been created for the private repository using the command `git submodule add <URL of the private repository> remote`.
-   The repositories have been added to ArgoCD Repositories in "Settings" to allow ArgoCD to access them.
-   A Kubernetes secret has been created in the default and argocd namespace with the personal access token of the private repository using the command `kubectl create secret generic <secret-name> --from-literal=token=<personal-access-token> --namespace=<namespace>`.

To update the submodule:

1.  Run `git submodule update --init` to ensure that the submodule is up to date.
2.  Navigate to the `remote` directory using the command `cd remote`.
3.  Checkout the `main` branch of the submodule using the command `git checkout main`.
4.  Navigate back to the root directory using the command `cd ..`.
5.  Add the `remote` submodule using the command `git add remote`.
6.  Commit the changes with the message "Update remote submodule" using the command `git commit -m "Update remote submodule"`.

In addition, the following tools have been installed and configured for the Kubernetes cluster:

-   AWS EBS CSI Driver (to attach Elastic block storage to pods in k8s with storage classes, pv, and pvc) has been installed using the command `kubectl apply -k "github.com/kubernetes-sigs/aws-ebs-csi-driver/deploy/kubernetes/overlays/stable/?ref=release-1.16"`.
    
-   Ingress Nginx controller for k8s cluster has been installed using the following commands:
    
    1.  `helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx`
    2.  `helm repo update`
    3.  `helm install nginx-ingress ingress-nginx/ingress-nginx --set controller.publishService.enabled=true`

These tools are necessary for the proper functioning of the Kubernetes cluster and the application being deployed.
