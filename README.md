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


# Please , make sure you have kubectl installed.
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
```
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```
```
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```
```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
```
mkdir -p ~/.local/bin/kubectl
```
```
mv ./kubectl ~/.local/bin/kubectl
```
### check kubectl version to make sure it is installed
```
kubectl version --client
```
