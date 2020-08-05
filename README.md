# kubePlaybook
Ansible Playbook for standing up a basic kubernetes cluster

CentOS 7 is currently not supported due to overlay storage drivers and using xfs fstype=0.
## Usage

```
$ ansible-playbook -i inventory/hosts new-cluster.yml
```

### Example Inventory file
```
flynshue[1:3]c.mylabserver.com

[kube_master]
flynshue1c.mylabserver.com

[kube_nodes]
flynshue2c.mylabserver.com
flynshue3c.mylabserver.com
```

### Can specify docker and kube versions
```
roles/kube-common/vars
---
docker_version: "5:19.03.12~3-0~ubuntu-bionic"
kube_version: "1.17.8-00"
```
Or
```
ansible-playbook -i inventory/hosts new-cluster.yml -e docker_version=5:19.03.12~3-0~ubuntu-bionic -e kube_version=1.17.8-00
```