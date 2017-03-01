# besserberg

helm chart for [besserberg](https://github.com/Vnet-as/besserberg).

Before you start make sure you have `vnet` [chart repository enabled](https://github.com/Vnet-as/charts).


## Installation

Installing charts is very easy as you can see in example bellow:

```bash
$ helm install --name johannes vnet/besserberg
NAME:   johannes
NAMESPACE: default
STATUS: DEPLOYED

RESOURCES:
==> v1/ConfigMap
NAME                  DATA      AGE
johannes-besserberg   1         0s

==> v1/Service
NAME                  CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
johannes-besserberg   10.0.0.11    <none>        80/TCP    0s

==> extensions/Deployment
NAME                  DESIRED   CURRENT   UP-TO-DATE   AVAILABLE   AGE
johannes-besserberg   1         1         1            0           0s
```

Let's verify that application is deployed in kubernetes.

```bash
$ kubectl get pods
NAME                                   READY     STATUS    RESTARTS   AGE
johannes-besserberg-1832809726-3hzsr   2/2       Running   0          1m
```

## Values

By default service type is set to `ClusterIP` which can be overrided by `service.type` value.

```bash
$ helm install --set service.type=NodePort vnet/besserberg
```

You can also specify node port that kubernetes would assign to the service by settings `service.nodePort` value.

```bash
$ helm install --set service.type=NodePort,service.nodePort=30030 vnet/besserberg
```

For more value overrides see [values.yml](https://github.com/Vnet-as/charts/blob/master/besserberg/values.yaml)
