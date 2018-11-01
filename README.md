# kubernetes_sample

## catchup

- [Foundational - Kubernetes](https://kubernetes.io/docs/user-journeys/users/application-developer/foundational/#section-2)
- [Viewing Pods and Nodes - Kubernetes](https://kubernetes.io/docs/tutorials/kubernetes-basics/explore/explore-intro/)


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
$ kubectl get pods -l app=nginx
NAME                                READY     STATUS    RESTARTS   AGE
nginx-deployment-75675f5897-4xprw   1/1       Running   0          3m
nginx-deployment-75675f5897-6q4kk   1/1       Running   0          3m
```

- describe pod

```
$ kubectl describe pod nginx-deployment-75675f5897-4xprw
```
