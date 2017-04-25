Role Name
=========

An [Ansible] role to deploy a [Kubernetes] - K8s Cluster

- [Weave-Net] is used for the network overlay currently

Requirements
------------

Install additional required [Ansible] roles:

```
sudo ansible-galaxy install -r requirements.yml
```

Role Variables
--------------

```
---
# defaults file for ansible-k8s
#
k8s_admin_config: '/etc/kubernetes/admin.conf'

# Define Ansible group which defines the K8s Cluster
k8s_advertise_address_int: 'enp0s8'

k8s_advertise_bind_port: '6443'

k8s_cluster_group: 'k8s'

k8s_dashboard: 'https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/kubernetes-dashboard.yaml'

k8s_debian_packages:
  - 'kubelet'
  - 'kubeadm'
  - 'kubectl'
  - 'kubernetes-cni'

k8s_debian_repo_info:
  key: '{{ k8s_package_url }}/apt/doc/apt-key.gpg'
  repo: 'deb http://apt.kubernetes.io/ kubernetes-{{ ansible_distribution_release|lower }} main'

# https://github.com/kubernetes/helm
k8s_helm_install: false

k8s_helm_install_dir: '/usr/local/bin'

k8s_helm_package: 'helm-v{{ k8s_helm_version }}-linux-amd64.tar.gz'

k8s_helm_url: 'https://kubernetes-helm.storage.googleapis.com'

k8s_helm_version: '2.3.0'


k8s_package_url: 'https://packages.cloud.google.com'

k8s_pod_network_config: 'https://git.io/weave-kube-1.6'

k8s_reset_cluster: false

# Defines services which should be enabled on boot
k8s_services:
  - 'kubelet'

k8s_token_file: '/etc/kubernetes/.k8s_token'

k8s_users:
  - user: 'vagrant'
```

Dependencies
------------

None

Example Playbook
----------------

```
---
- hosts: k8s
  # become: true
  vars:
    # Define Docker version to install
    docker_version: '1.12.6'
    # Defines if all nodes in play should be added to each hosts /etc/hosts
    etc_hosts_add_all_hosts: true
    etc_hosts_pri_dns_name: '{{ pri_domain_name }}'
    # Defines if node has static IP.
    etc_hosts_static_ip: true
    # Defines if ansible_default_ipv4.address is used for defining hosts
    etc_hosts_use_default_ip_address: false
    # Defines if ansible_ssh_host is used for defining hosts
    etc_hosts_use_ansible_ssh_host: true
    pri_domain_name: 'test.vagrant.local'
  roles:
    - role: ansible-etc-hosts
    - role: ansible-change-hostname
    - role: ansible-docker
    - role: ansible-k8s
  tasks:
```

Vagrant
-------

- Requirements
  - [Ansible]
  - [Vagrant]
  - [Virtualbox]

Included in the `Vagrant` folder is a testing environment with `3` nodes.
- `node0` - K8s Cluster Master (`192.168.250.10`)
- `node1` - K8s Cluster Member (`192.168.250.11`)
- `node2` - K8s Cluster Member (`192.168.250.12`)

You can easily spin this up for learning purposes:
```
cd Vagrant/
vagrant up
```

Once the environment spins up you will see the following:
```
TASK [ansible-k8s : cluster_summary | Displaying Cluster Nodes] ****************
skipping: [node1]
ok: [node0] => {
    "_k8s_cluster_nodes['stdout_lines']": [
        "NAME      STATUS     AGE       VERSION",
        "node0     Ready      1m        v1.6.1",
        "node1     NotReady   4s        v1.6.1",
        "node2     NotReady   6s        v1.6.1"
    ],
    "changed": false
}
skipping: [node2]
```
Do not worry about the above as the additional nodes did not completely join
the cluster before the provisioning completed. You can quickly validate that
the additional nodes are up and `Ready` by running:
```
ansible-playbook -i hosts playbook.yml --tags k8s_cluster_nodes
```
```
TASK [ansible-k8s : cluster_summary | Displaying Cluster Nodes] ****************************************************************************************************************
skipping: [node1]
ok: [node0] => {
    "_k8s_cluster_nodes['stdout_lines']": [
        "NAME      STATUS    AGE       VERSION",
        "node0     Ready     7m        v1.6.1",
        "node1     Ready     6m        v1.6.1",
        "node2     Ready     6m        v1.6.1"
    ],
    "changed": false
}
skipping: [node2]
```

Once the cluster is up `ssh` to `node0` and begin playing:
```
vagrant ssh node0
```

When you are all done using the environment easily tear it down:
```
./cleanup.sh
```
```
==> node2: Forcing shutdown of VM...
==> node2: Destroying VM and associated drives...
==> node1: Forcing shutdown of VM...
==> node1: Destroying VM and associated drives...
==> node0: Forcing shutdown of VM...
==> node0: Destroying VM and associated drives...
```

Additional Info
---------------
- Reset `K8s` cluster
  - `ansible-playbook -i hosts playbook.yml --tags k8s_reset -e "k8s_reset_cluster=true"`

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

[Ansible]: <https://www.ansible.com>
[Kubernetes]: <https://kubernetes.io>
[Vagrant]: <https://www.vagrantup.com/>
[Virtualbox]: <https://www.virtualbox.org/>
[Weave-Net]: <https://www.weave.works/docs/net/latest/kube-addon/>
