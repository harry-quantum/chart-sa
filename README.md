helm create chart-sa
cd chart-sa

helm lint .
helm template .

helm init
helm install --name sa .

helm ls -a



helm repo update hw .
does not seem to make any changes

kubectl get deploy/hw-hello-world -o yaml

helm delete --purge hw
release "hw" deleted