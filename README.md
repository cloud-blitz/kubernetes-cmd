__Common Commands__
```shell
kubectl run --generator=run-pod/v1 --rm mytest --image=yauritux/busybox-curl -it
```
```shell
kubectl run --generator=run-pod/v1 --rm mytest --image=busybox -it wget
```
```shell
kubectl run my-nginx --image=nginx --replicas=2 --port=80
```
```shell
kubectl run my-nginx --restart=Never --image=nginx --port=80 --expose
```
```shell
kubectl run my-nginx --image=nginx --port=80 --expose
```
```shell
kubectl config get-contexts, ~/.kube/config
```
```shell
kubectl config set-context <context_name> --namespace=<ns_name>
```
```shell
kubectl get pod -o wide
```
```shell
kubectl get all --all-namespaces
```
```shell
kubectl get service --all-namespaces
```
```shell
kubectl get deployments --all-namespaces
```
```shell
kubectl get nodes --show-labels
```
```shell
kubectl get pods --all-namespaces -o json
```
```shell
kubectl create --dry-run --validate -f pod-dummy.yaml
```
```shell
kubectl run --rm -i -t --image=alpine test-$RANDOM -- sh
```
```shell
kubectl exec -it mytest -- ls -l /etc/hosts
```
```shell
kubectl -n kube-system get cm kubeadm-config -o yaml
```
```shell
kubectl -n denny-websites get deployment mysql -o yaml
```
```shell
kubectl explain pods, kubectl explain svc
```
```shell
kubectl get pods  -n wordpress --watch
```
```shell
curl -L http://127.0.0.1:10250/healthz
```
```shell
kubectl exec -it storage sh
```
```shell
kubectl exec redis-master-ft9ex env
```
```shell
echo "source <(kubectl completion bash)" >>~/.bashrc
```
```shell
eval $(minikube docker-env)
```
```shell
kubectl apply -R -f .
```
```shell
kubectl get services –sort-by=.metadata.name
```
```shell
kubectl get pods –sort-by=’.status.containerStatuses[0].restartCount’
```
```shell
kubectl get pods -o=’custom-columns=PODS:.metadata.name,Images:.spec.containers[*].image’
```
```shell
#!/bin/bash
kubectl get pods --all-namespaces -o jsonpath="{..image}" |\
tr -s '[[:space:]]' '\n' |\
sort |\
uniq -c
```
__Check Performance__
```shell
kubectl top node
```
```shell
kubectl top node
```
```shell
kubectl top <podname> --containers
```
```shell
kubectl top pod --all-namespaces --containers=true
```
__Resources Deletion__
```shell
kubectl delete pod/<pod-name> -n <my-namespace>
```
```shell
kubectl delete pod/<pod-name> --grace-period=0 --force
```
```shell
kubectl delete pod -l env=test
```
```shell
kubectl delete deployment -l app=wordpress
```
```shell
kubectl delete pods,services -l name=myLabel
```
```shell
kubectl -n my-ns delete po,svc --all
```
```shell
kubectl delete pvc -l app=wordpress
```
```shell
kubectl delete sts/<stateful_set_name> --cascade=false
```
__POD__
```shell
kubectl get pods
```
```shell
kubectl get pods --all-namespaces
```
```shell
kubectl get -n kube-system pods -a
```
```shell
kubectl get pod -o wide, kubectl get pod/<pod-name> -o yaml
```
```shell
kubectl describe pod/srv-mysql-server
```
```shell
kubectl get pods --show-labels
```
```shell
kubectl get pods –field-selector=status.phase!=Running –all-namespaces
```
```shell
kubectl get pods –field-selector=status.phase=Running
```
```shell
kubectl get pod --template '{{.status.initContainerStatuses}}' <pod-name>
```
```shell
kubectl exec -it -n “$ns” “$podname” – sh -c “echo $msg >>/dev/err.log”
```
```shell
kubectl get pods  -n wordpress --watch
```
```shell
kubectl get pods –selector=”app=syslog” -o jsonpath=’{.items[*].metadata.name}’
```
```shell
kubectl get pods -o=’custom-columns=PODS:.metadata.name,Images:.spec.containers[*].image’
```
```shell
kubectl get pods -l owner=denny
```
```shell
kubectl get pods -l owner=denny
```
```shell
kubectl label pods dummy-input owner-
```
```shell
kubectl annotate pods dummy-input my-url=https://dennyzhang.com
```
__Deployment & Scale__
```shell
kubectl scale --replicas=3 deployment/nginx-app
```
```shell
kubectl rollout app-v1 app-v2 --image=img:v2
```
```shell
kubectl rollout app-v1 app-v2 --rollback
```
```shell
kubectl get rs
```
```shell
kubectl rollout status deployment/nginx-app
```
```shell
kubectl rollout history deployment/nginx-app
```
```shell
kubectl rollout pause deployment/nginx-deployment, resume
```
```shell
kubectl rollout undo deployment/nginx-deployment
```

