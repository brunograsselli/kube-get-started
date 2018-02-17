# Get started - Kubernetes

I am using this repository to do some experiments with Kubernetes.

## Installing Kubernetes

I installed Kubernetes on Digital Ocean VMs following this guide:

https://kubernetes.io/docs/setup/independent/create-cluster-kubeadm/

## Deployment

The following command create a deployment with a replica set and pods of nginx containers (https://kubernetes.io/docs/tasks/run-application/run-stateless-application-deployment/).
```shell
kubectl --kubeconfig ./admin.conf apply -f nginx.yml
```

This creates a service with a random port. This is used to expose the service to the outside.
```shell
kubectl --kubeconfig ./admin.conf expose rs nginx-deployment-6c54bd5869 --port=80 --type="NodePort"
```

In order to see the exposed port:
```shell
kubectl --kubeconfig ./admin.conf describe service nginx-deployment-6c54bd5869
```
