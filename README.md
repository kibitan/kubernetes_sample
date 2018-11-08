# kubernetes_sample

## catchup

- [Foundational - Kubernetes](https://kubernetes.io/docs/user-journeys/users/application-developer/foundational/#section-2)
- [Viewing Pods and Nodes - Kubernetes](https://kubernetes.io/docs/tutorials/kubernetes-basics/explore/explore-intro/)
- [Kubernetes Components - Kubernetes](https://kubernetes.io/docs/concepts/overview/components/)
- Configset: [Configure a Pod to Use a ConfigMap - Kubernetes](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/)
- Secret: [Secrets - Kubernetes](https://kubernetes.io/docs/concepts/configuration/secret/)
- Namespace: [Namespaces Walkthrough - Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/namespaces-walkthrough/)

## tutorials

- [Example: Deploying PHP Guestbook application with Redis - Kubernetes](https://kubernetes.io/docs/tutorials/stateless-application/guestbook/)

## useful tool

- [Web UI (Dashboard) - Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)

```
$ kubectl create -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml

$ kubectl proxy

$ open http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/login


## cleanup
$ kubectl delete -f https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml
```

## cheetsheet

### kubectl

- apply configuration

```
$ kubectl apply -f stateless-application/deployment.yaml
deployment.apps "nginx-deployment" created
```

- show detail of deployment

```
$ kubectl describe deployment nginx-deployment
Name:                   nginx-deployment
Namespace:              default
CreationTimestamp:      Thu, 01 Nov 2018 14:58:43 +0100
....
```

- list pods

```
$ kubectl get pods -l <selector>
NAME                                READY     STATUS    RESTARTS   AGE
nginx-deployment-75675f5897-4xprw   1/1       Running   0          3m
nginx-deployment-75675f5897-6q4kk   1/1       Running   0          3m
```

- describe pod

```
$ kubectl describe pod nginx-deployment-75675f5897-4xprw
```


- describe PersistentVolumeClaim

```
$ kubectl describe pvc <pvc name>
```

- running temporary interactive container in pod

```
$ kubectl run -it --rm --image=mysql:5.6 --restart=Never <name> -- <command>

e.g.

kubectl run -it --rm --image=mysql:5.6 --restart=Never mysql-client -- mysql -h mysql -ppassword
```


- delete deployed objects

```
kubectl delete deployment
```
