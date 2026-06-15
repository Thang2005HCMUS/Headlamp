```YAML
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: root-headlamp
  namespace: argocd
spec:
  project: default
  source:
    repoURL: 'https://github.com/<USER_CỦA_BẠN>/<REPO_CỦA_BẠN>.git'
    targetRevision: HEAD # Hoặc 'main'
    path: . # Đường dẫn đến thư mục chứa file headlamp-app.yaml
  destination:
    server: 'https://kubernetes.default.svc'
    namespace: argocd
  syncPolicy:
    automated: {}
```