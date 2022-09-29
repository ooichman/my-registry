# my-registry

A simple Kustomize deployment for Container image registry on to of Kubernetes/OpenShift

## deployment

clone the git repository :
```bash
$ git clone https://github.com/ooichman/my-registry
$ cd my-registry
```
and Create the namespace :
```bash
$ kubectl create ns my-registry
```
**alternative**

you can create it on Openshift as well with the following command :
```bash
$ oc new-project my-registry
```

### kubernetes
For Kubernetes run the following command :
```bash
$ kubectl -k overlays/kubernetes/
```

### OpenShift

For OpenShift Because we are working with a route resource and not an ingress resource run :
```bash
$ oc -k overlays/openshift/
```

The default username/password are myuser/mypassword (you can change them by modifing the secret file
in the base directory


