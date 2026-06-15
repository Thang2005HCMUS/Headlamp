```YAML
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: headlamp
  namespace: argocd
spec:
  project: default
  source:
    repoURL: 'https://github.com/Thang2005HCMUS/Headlamp.git' # Repo của bạn
    targetRevision: main
    path: k8s # Trỏ vào folder k8s
  destination:
    server: https://kubernetes.default.svc
    namespace: headlamp-app
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```