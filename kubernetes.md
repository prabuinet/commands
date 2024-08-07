## Kubernetes

## apply yaml file 
kubectl apply -f [configfile-filename]

kubectl apply -f posts.yaml

## list pods
kubectl get pods

## execute command in a pod
kubectl exec [pod-name] -it -- [cmd]

kubectl exec posts -it -- sh

## logs
kubectl logs [pod-name]

kubectl logs posts

## delete pod
kubectl delete pod [pod-name]

kubectl delete pod posts

## describe
kubectl describe pod [pod-name]

kubectl describe pod posts

