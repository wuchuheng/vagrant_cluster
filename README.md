<h1 align="center"> vagrant_k8s_cluster </h1>
Kubernetes setup using vagrant

## Prerequisites
* Vagrant 
* virtualbox
* land network

## Usage
Step 1: to clone the repository
``` bash
$ git clone https://github.com/wuchuhengtools/vagrant_k8s_cluster.git
$ cd vagrant_k8s_cluster
```
Step 2: to configure the Land network with `Vagrantfile` 
``` yaml
...
  masterIp = "192.168.0.200"  # <-- the ip for master node
  # configures the group of node ip 
  nodesIP =  [ 
    "192.168.0.201", # <-- the ip for work node
    "192.168.0.202",
    ...
  ]
  ...
```

Step 3:  start up the cluster 
``` bash 
$ vagrant up # <-- initialization cluster 
$ vagrant ssh master
$ sudo su
# kubectl get nodes # <-- show the k8s cluster
NAME     STATUS   ROLES                  AGE   VERSION
master   Ready    control-plane,master   19h   v1.21.3
node0    Ready    <none>                 18h   v1.21.3
node1    Ready    <none>                 18h   v1.21.3
```

## Contributing

You can contribute in one of three ways:

1. File bug reports using the [issue tracker](https://github.com/wuchuhengtools/vagrant_k8s_cluster/issues).
2. Answer questions or fix bugs on the [issue tracker](https://github.com/wuchuheng/vagrant_k8s_cluster/issues).
3. Contribute new features or update the wiki.

_The code contribution process is not very formal. You just need to make sure that you follow the PSR-0, PSR-1, and PSR-2 coding guidelines. Any new code contributions must be accompanied by unit tests where applicable._

## License

MIT