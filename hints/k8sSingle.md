# Single Container app in K8s

**Hint: You have to install kubectl first!**

1. Run single container app in your K8s cluster (this method is deprecated now, but is a nice way to get started)
```
kubectl run --generator=run-pod/v1 nginx --image=nginx
```
2. See what you got
```
kubectl get pods  
kubectl describe pods  
kubectl get deployments
```
3. Wrap your pod deployment with service 
```
kubectl expose deployment nginx --port=80
```
4. See what you got
```
kubectl get deployment
kubectl get service
```
5. Edit your service to be able to be accessed from the public internet
```
kubectl edit service/nginx
```
6. This opens up an editor. Exchange ClusterIp to LoadBalancer. Close and save the file.
7. Check the state of your service
```
kubectl get service -w
```
8. Wait until your Service got a public address. Then type this address into your webbrowser.
