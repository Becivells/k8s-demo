## minikube 安装


##环境
macOS vmware

[访问地址](https://minikube.sigs.k8s.io/docs/start/)

```shell
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
sudo install minikube-darwin-amd64 /usr/local/bin/minikube
```
一定要使用国内源。代理会有很多问题

```shell
minikube start --driver=vmware  --image-mirror-country='cn'
```

mac 下地址
```shell
source <(kubectl completion zsh)
source <(minikube completion zsh)
# alias kubectl="minikube kubectl --"
```

开启 ingress
```shell
 minikube addons enable ingress
```

## demo 演示

```shell
kubectl apply -f nginx-dp.yaml
kubectl apply -f nginx-svc.yaml
kubectl apply -f nginx-ingress.yaml 
```

## 查看pod
```shell
kubectl get pod
```

## 查看 service
```shell
kubectl get svc

```

查看 ingress
```shell
kubectl get ingress 
```

## 查看 ip
```shell
minikube ip
```

## 查看 url
```shell
minikube service --url nginx-svc

```

```shell
kubectl get pods --namespace=ingress-nginx
```