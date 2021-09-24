```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: hello
  namespace: ntl-geekfest
spec:
  project: default
  source:
    repoURL: 'https://github.com/theriaultnicolas/geekfest.git'
    path: app-of-apps
    targetRevision: HEAD
  destination:
    server: 'https://kubernetes.default.svc'
    namespace: ntl-geekfest
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```