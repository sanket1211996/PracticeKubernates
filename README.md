# Kubernates dashboard config:
STEP 1: kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.5.0/aio/deploy/recommended.yaml

STEP 2: kubectl describe secret -n kube-system
## Copy token under name: kubernetes.io/service-account-token

STEP 3: kubectl proxy
STEP 4: Open http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

STEP 5: Paste the token

# Kubernates Create Pod:
kubectl run [podname] --image=nginx:alpine
# Kubectl list only pods:
kubectl get pods
# Kubectl all resources:
kubectl get all
# kubectl port-forward:
kubectl port-forward [podname] 8080:80
# kubectl delete pod:(will recreate)
kubectl delete pod [podname]
# kubectl delete deployment permenanet:
kubectl delete deployement [podname]

