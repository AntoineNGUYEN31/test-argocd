Argo resrouce file for a helm deployment

```
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: test-helm
spec:
  destination:
    name: ''
    namespace: default
    server: 'https://kubernetes.default.svc'
  source:
    path: helm
    repoURL: 'https://github.com/AntoineNGUYEN31/test-argocd.git'
    targetRevision: main
    helm:
      valueFiles:
        - values.yaml
  project: default
  syncPolicy:
    automated:
      prune: false
      selfHeal: false
```
