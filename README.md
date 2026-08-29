# Configuration of the DevOps with Kubernetes project

The application code lives in https://github.com/Rororo06/devops. This
repository contains the Kubernetes configuration that ArgoCD deploys:

- `base` the manifests shared by all the environments
- `overlays/staging` the staging environment in the namespace `project-staging`
- `overlays/production` the production environment in the namespace
  `project-production`
- `argocd/project-application.yaml` the ArgoCD applications of both environments

The GitHub Actions workflows of the code repository build the images and commit
the new image tags to the overlays of this repository. The secrets
`postgres-secret` and `broadcaster-secret` are applied outside of ArgoCD.
