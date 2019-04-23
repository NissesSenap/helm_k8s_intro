# Commands

### Create base repo (windows)
mkdir -p development\my-first-helm-chart\manifests

### Create the deployment for nginx
kubectl run example --image=nginx:1.13.5-alpine -o yaml > manifests/deployment.yaml

### Create the service
kubectl expose deployment example --port=80 --type=NodePort -o yaml > manifests/service.yaml

### Expose the minikube url
### NOTE this only works from the powershell admin terminal
minikube service example --url

### Cleanup stuff
kubectl delete -f manifests

### Initialise helm
helm init

### Create the repo
helm create helm

Uppgrade the files according to the blog

### Get the minikube url
minikube service second --url

### Upgrade helm with a new tag
helm upgrade --set image.repository=httpd --set image.tag=2.2.34-alpine second helm

### Change in values.yaml replica count to 3
helm upgrade second helm