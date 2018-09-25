# istioworkshop


#### Start

Then you can distribute this box for sharing. For example on another machine:

- install virtualbox  and vagrant
- copy  Vagrantfile and kubeadm-v.11.box to your machine
  scp -r xxx@9.46.64.12:/root/istioworkshop/ ./
- vagrant box add kubeadm-v1.11.box --name kubeadm-v1.11
- vagrant up

#### Access

Up till now you should be to access the cluster either from inside the cluster, or on the host machine:

- from inside
    - vagrant ssh
    - wait for a few while to let the kube api server get started. "ps -ef|grep apiserver"
    - kubectl get node
- from outside, on the host machine
    - mkdir ~/.kube
    - scp -P 2222 vagrant@127.0.0.1:/home/vagrant/.kube/config ~/.kube/ (password is "vagrant")
    - optional: if kubectl is not installed:
        - curl -L https://storage.googleapis.com/kubernetes-release/release/v1.11.3/bin/linux/amd64/kubectl -o /usr/local/bin/kubectl
        - chmod +x /usr/local/bin/kubectl
    - kubectl get node

---
#### Make the workshop use the existing docker images instead of pulling off from website

#### Package an exsiting k8s running env 

Firstly package the running env into a vagrant box:

- vagrant package --base kubeadm-v1.11 --output kubeadm-v1.11.box
