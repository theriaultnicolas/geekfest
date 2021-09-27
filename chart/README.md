source : https://github.com/axdotl/spring-petclinic-helm
```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: echo
  namespace: ntl-geekfest
spec:
  project: default
  source:
    repoURL: 'https://theriaultnicolas.github.io/geekfest/'
    targetRevision: 2.0.0
    chart: echo
  destination:
    server: 'https://kubernetes.default.svc'
    namespace: ntl-geekfest
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```