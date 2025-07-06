# Platform GitOps Repository

This repository manages the **infrastructure platform** components of our Kubernetes cluster using **GitOps** principles with [Argo CD](https://argo-cd.readthedocs.io/).

---

## 📦 Structure

```bash
.
├── apps/              # Argo CD Applications (e.g., cert-manager, ingress-nginx)
│   └── <app-name>/
│       └── app.yaml
├── projects/          # Argo CD AppProjects (e.g., platform)
│   └── platform.yaml

```
## 🚀 GitOps with Argo CD

Argo CD watches this repository and syncs changes automatically to the cluster.

To add a new infrastructure component:

    Add a folder under apps/your-app/

    Define an app.yaml using a Helm chart or Kustomize

    Commit and push — Argo CD will auto-sync


## 🔐 Security Notes

    This repo assumes Argo CD has access to Helm chart repos and (if private) GitHub SSH credentials configured.

    Secrets and sensitive data should be stored separately using Sealed Secrets, SOPS, or your secrets manager of choice.