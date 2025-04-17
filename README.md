# my-registry

A simple Kustomize deployment for Container image registry on to of Kubernetes/OpenShift

## deployment

clone the git repository :
```bash
git clone https://github.com/ooichman/my-registry && cd my-registry
```

and Create the namespace :
```bash
kubectl create ns my-registry && \
kubectl config set-context --current --namespace=my-registry
```

**alternative**

you can create it on Openshift as well with the following command :
```bash
oc new-project my-registry
```

### Environment Variables
Before we start the deployment we need to setup the REGISTRY_FQDN environment variable:

```bash
export REGISTRY_FQDN="registry.example.com"
```


### kubernetes / OpenShift
For Kubernetes run the following command :
```bash
kustomize build overlays/kubernetes/ | envsubst | kubectl apply -f -
```
Or for OpenShift
```bash
kustomize build overlays/openshift/ | envsubst | oc apply -f -
```

The default username/password are myuser/mypassword (you can change them by modifing the secret file
in the base directory


