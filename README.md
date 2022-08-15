# Connecting-to-kubernetes-cluster
## Create a file on ~/.kube/config
```
mkdir -p ~/.kube
```
## vim to the config file in .kube
```
vi -p ~/.kube/config
```
## copy and paste the below
```
apiVersion: v1
kind: Config
clusters:
- cluster:
    certificate-authority-data: {cluster-ca}
    server: {server-dns}
  name: {cluster-name}
users:
- name: {user-name}
  user:
    token: {secret-token}
contexts:
- context:
    cluster: {cluster-name}
    user: {user-name}
  name: {context-name}
current-context: {context-name}


```
## let update the entries with what we received from the kubernetes adminstrator
