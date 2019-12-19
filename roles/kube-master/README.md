Role Name
=========

Initialize kube cluster, provision pod network, create .kube/config files and install flannel.  

Requirements
------------

Requires kubeadm, kubectl, and kubeadm to be installed. Use kube-common role to install packages.

Role Variables
--------------

  ```
  kube_user: userName
  pod_network_cidr: "10.244.0.0/16"
  ```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: kube-master, kube_user: "{{ lookup('env', 'USER') }}" }

License
-------

MIT


