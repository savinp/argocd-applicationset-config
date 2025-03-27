# argocd-applicationset-config

ArgoCD in Orielly ---

kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'


kubectl get svc -n argocd

argocd-server                             NodePort    10.104.126.167   <none>        80:30535/TCP,443:30432/TCP   9m

Access through node port--

The belo change in must--

kubectl edit configmap argocd-cmd-params-cm -n argocd

data:
  server.insecure: "true"
  
kubectl rollout restart deployment argocd-server -n argocd


  
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
