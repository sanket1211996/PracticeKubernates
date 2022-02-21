# Kubernates dashboard config:
STEP 1: kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.5.0/aio/deploy/recommended.yaml

STEP 2: kubectl describe secret -n kube-system
## Copy token under name: kubernetes.io/service-account-token

STEP 3: kubectl proxy
STEP 4: Open http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

STEP 5: Paste the token

------Chapter: Create Pods---------

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

# Run YAML file to create pod & validate if work correctly:
kubectl create -f file.pod.yml --dry-run=client --validate=true
kubectl create -f nginx.pod.yml

# Apply YAML file, create if not already or update if already running:
kubectl apply -f file.pod.yml

# Use --save-config when you want to use
# kubectl apply in the future
kubectl create -f file.pod.yml --save-config
# Delete pod using YAML:
kubectl delete -f file.pod.yml
# Get pod config as yaml which was saved by --save-config flag
kubectl get pod my-nginx -o yaml
# Get Pod History:
kubectl describe pod my-nginx
# Run interactive shell, connecting to POD:
kubectl exec my-nginx -it sh
## TYPE exit to come to of shell
# To edit pod config:
kubectl edit -f file.pod.yml

# POD Probe Types:
ExecAction, TCPSocketAction, HTTPGetAction
# POD Probe State: Success, Failure, Unknown

-----------Kubernates Deployment-------------
# Kube Create Deployement
kubectl create -f nginx.deployment.yml 
# OR create and save config
kubectl create -f nginx.deployment.yml --save-config
# Kube Apply Deployement
kubectl apply -f nginx.deployment.yml 
# Kube describe deployment:
kubectl describe deployment my-nginx
# Kube Get Deployments:
kubectl get deployments
# Kube Get list of all labels:
kubectl get deployments --show-labels
# Kube Get deployement of specific label:
kubectl get deployments -l app=my-nginx
# Kube Delete Deployment:
kubectl delete deployment [deployment-name]
Eg. kubectl delete deployment my-nginx
# OR
Eg. kubectl delete -f nginx.deployment.yml
# Kube Scale Deployement:
kubectl scale deployment [deployment-name] --replicas=5
Eg. kubectl scale deployment my-nginx --replicas=5
# OR by filename
kubectl scale -f nginx.deployment.yml --replicas=5
# OR update in spec of YAML file
 

