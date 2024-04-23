Встановлення ArgoCD за допомогою Helm:
Спочатку вам потрібно встановити Helm у вашому Kubernetes кластері. Ви можете знайти інструкції щодо цього в офіційній документації Helm.
Потім додайте репозиторій ArgoCD до Helm:
  helm repo add argo https://argoproj.github.io/argo-helm
  helm repo update
Використайте наступну команду, щоб встановити ArgoCD, використовуючи Helm:
  helm install argocd argo/argo-cd
Налаштування доступу до графічного інтерфейсу ArgoCD:
Після встановлення ArgoCD, отримайте доступ до графічного інтерфейсу (Web UI). Зазвичай це можна зробити, відкривши ArgoCD за допомогою служби типу NodePort або LoadBalancer.
Щоб знайти IP-адресу або URL-адресу, за якою можна отримати доступ до ArgoCD, використайте команду:
  kubectl get svc argocd-server -n argocd
Після отримання IP-адреси або URL-адреси, відкрийте веб-браузер та перейдіть за цією адресою.
Під час першого входу вам може знадобитися логін та пароль. Ви можете знайти їх, використовуючи команду:
  kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" 
