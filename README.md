# DOCUMENTATION
Documentation for RSO project

## Docker

* ``` 
  docker rmi $(docker images -f “dangling=true” -q)
  ​```// removes all untaged images
  ```
 * ``` docker network create rso1920 ``` // create rso1920 network
 * ``` docker run -d -p 2379:2379 --name etcd --network rso1920 --volume=/tmp/etcd-data:/etcd-data quay.io/coreos/etcd:latest /usr/local/bin/etcd --name my-etcd-1 --data-dir /etcd-data --listen-client-urls http://0.0.0.0:2379 --advertise-client-urls http://0.0.0.0:2379 --listen-peer-urls http://0.0.0.0:2380 --initial-advertise-peer-urls http://0.0.0.0:2380 --initial-cluster my-etcd-1=http://0.0.0.0:2380 --initial-cluster-token my-etcd-token --initial-cluster-state new --auto-compaction-retention 1 -cors="*" ``` // docker etcd server
 * ``` docker run -d -p 9080:8080 nikfoundas/etcd-viewer ``` 

 ## Ingres
 * https://learnk8s.io/kubernetes-ingress-api-gateway/
 * https://github.com/Kong/kubernetes-ingress-controller/blob/master/docs/guides/getting-started.md
 * https://docs.konghq.com/1.4.x/kong-kubernetes/install/