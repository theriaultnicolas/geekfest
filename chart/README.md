source : https://github.com/axdotl/spring-petclinic-helm
```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: hello
  namespace: ntl-argocd
spec:
  destination:
    namespace: ntl-argocd
    server: 'https://kubernetes.default.svc'
  project: default
  source:
    chart: hello
    helm:
      parameters:
        - name: nameOverride
          value: ntl
    repoURL: 'https://cloudecho.github.io/charts/'
    targetRevision: 0.1.1
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```