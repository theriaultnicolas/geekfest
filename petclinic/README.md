```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: petclinic
  namespace: ntl-geekfest
spec:
  destination:
    namespace: ntl-geekfest
    server: 'https://kubernetes.default.svc'
  project: default
  source:
    path: petclinic
    repoURL: 'https://github.com/theriaultnicolas/geekfest.git'
    targetRevision: HEAD
  syncPolicy: {}
```
