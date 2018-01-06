# kubernetes-vagrant
deploy 1 master 2 worker nodes k8s cluster

all you need to do is just run
```
$ vagrant up
```

result
```
[root@kubemaster ~]# kubectl  get nodes
NAME                    STATUS    ROLES     AGE       VERSION
kubeagent-one.hdp.com   Ready     <none>    2h        v1.9.1
kubeagent-two.hdp.com   Ready     <none>    1m        v1.9.1
kubemaster.hdp.com      Ready     master    2h        v1.9.1
```

you can add as many as worker nodes you want

just need to put it in group_vars/all -> `hostsLine`
