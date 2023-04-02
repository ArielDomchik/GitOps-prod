# GitOps-prod
- Create a submodule to the private repository
- Set up argo-cd to connect the private repo in "settings"
- Add kubernetes secret on the defualt and argocd namespace with the personal access token of private repository


  How to update the submodule

  `git submodule update --init
   cd value
   git checkout master
   cd ..
   git add value
   git commit -m "Update value submodule`
