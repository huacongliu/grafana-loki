# grafana-loki
k8s v1.22 集群内部署 grafana 与 loki

## 1.dev-k8s-master-1服务器创建存储目录
mkdir /data/grafana

mkdir /data/loki

chmod 777 /data/grafana

chmod 777 /data/loki


## 2.部署loki 日志服务
master1上执行

kubectl create namespace loki

kubectl label node dev-k8s-master-1 loki=true

kubectl apply -f loki.yaml

kubectl apply -f grafana.yaml


## 3.目前使用本地host存储数据，如果集群内有storageclass，可以修改执行loki-pvc.yaml，并修改另外两个文件适配服务文件
