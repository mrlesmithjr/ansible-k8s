# Vagrant

- Requirements
  - [Ansible](https://www.ansible.com)
  - [Vagrant](https://www.vagrantup.com/)
  - [Virtualbox](https://www.virtualbox.org/)

Included in the `Vagrant` folder is a testing environment with `4` nodes.

- `k8s-master` - K8s Cluster Master (`192.168.250.10`)
- `k8s-worker-01` - K8s Cluster Member (`192.168.250.11`)
- `k8s-worker-02` - K8s Cluster Member (`192.168.250.12`)
- `k8s-nfs-server` - K8s NFS Server (`192.168.250.13`)

You can easily spin this up for learning purposes:

```bash
cd Vagrant/
vagrant up
```

Once the environment spins up you will see the following:

```bash
TASK [ansible-k8s : cluster_summary | Displaying Cluster Nodes] ****************
ok: [k8s-master] => {
    "_k8s_cluster_nodes['stdout_lines']": [
        "NAME            STATUS   ROLES    AGE    VERSION",
        "k8s-master      Ready    master   103s   v1.17.5",
        "k8s-worker-01   Ready    <none>   33s    v1.17.5",
        "k8s-worker-02   Ready    <none>   33s    v1.17.5"
    ]
}
skipping: [k8s-worker-01]
skipping: [k8s-worker-02]
```

Do not worry about the above as the additional nodes did not completely join
the cluster before the provisioning completed. You can quickly validate that
the additional nodes are up and `Ready` by running:

```bash
ansible-playbook -i hosts playbook.yml --tags k8s_cluster_nodes
```

The above `NotReady` should no longer be an issue as we now wait for all nodes
in the cluster to become `Ready`. However, there may be an instance where this
may not work as expected.

```bash
TASK [ansible-k8s : cluster_summary | Displaying Cluster Nodes] **********************************************************************************************
ok: [k8s-master] => {
    "_k8s_cluster_nodes['stdout_lines']": [
        "NAME            STATUS   ROLES    AGE   VERSION",
        "k8s-master      Ready    master   14m   v1.17.5",
        "k8s-worker-01   Ready    <none>   13m   v1.17.5",
        "k8s-worker-02   Ready    <none>   13m   v1.17.5"
    ]
}
skipping: [k8s-worker-01]
skipping: [k8s-worker-02]
```

Once the cluster is up `ssh` to `k8s-master` and begin playing:

```bash
vagrant ssh k8s-master
```

When you are all done using the environment easily tear it down:

```bash
./cleanup.sh

==> node2: Forcing shutdown of VM...
==> node2: Destroying VM and associated drives...
==> node1: Forcing shutdown of VM...
==> node1: Destroying VM and associated drives...
==> node0: Forcing shutdown of VM...
==> node0: Destroying VM and associated drives...
```

## Additional Info

### Reset `K8s` cluster

```bash
ansible-playbook -i hosts playbook.yml --tags k8s_reset -e "k8s_reset_cluster=true"
```

### Get a list of pods and information on them

```bash
ansible-playbook -i hosts playbook.yml --tags k8s_pods
```

```bash
TASK [ansible-k8s : pods | Displaying Pods In All Namespaces] ************************************************************************************************
ok: [k8s-master] => {
    "msg": {
        "containers": [
            {
                "hostIP": "192.168.250.10",
                "image": "k8s.gcr.io/coredns:1.6.5",
                "name": "coredns",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "10.32.0.2",
                "resources": {
                    "limits": {
                        "memory": "170Mi"
                    },
                    "requests": {
                        "cpu": "100m",
                        "memory": "70Mi"
                    }
                }
            },
            {
                "hostIP": "192.168.250.10",
                "image": "k8s.gcr.io/coredns:1.6.5",
                "name": "coredns",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "10.32.0.3",
                "resources": {
                    "limits": {
                        "memory": "170Mi"
                    },
                    "requests": {
                        "cpu": "100m",
                        "memory": "70Mi"
                    }
                }
            },
            {
                "hostIP": "192.168.250.10",
                "image": "k8s.gcr.io/etcd:3.4.3-0",
                "name": "etcd",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "192.168.250.10",
                "resources": {}
            },
            {
                "hostIP": "192.168.250.10",
                "image": "k8s.gcr.io/kube-apiserver:v1.17.5",
                "name": "kube-apiserver",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "192.168.250.10",
                "resources": {
                    "requests": {
                        "cpu": "250m"
                    }
                }
            },
            {
                "hostIP": "192.168.250.10",
                "image": "k8s.gcr.io/kube-controller-manager:v1.17.5",
                "name": "kube-controller-manager",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "192.168.250.10",
                "resources": {
                    "requests": {
                        "cpu": "200m"
                    }
                }
            },
            {
                "hostIP": "192.168.250.11",
                "image": "k8s.gcr.io/kube-proxy:v1.17.5",
                "name": "kube-proxy",
                "nodeName": "k8s-worker-01",
                "phase": "Running",
                "podIP": "192.168.250.11",
                "resources": {}
            },
            {
                "hostIP": "192.168.250.12",
                "image": "k8s.gcr.io/kube-proxy:v1.17.5",
                "name": "kube-proxy",
                "nodeName": "k8s-worker-02",
                "phase": "Running",
                "podIP": "192.168.250.12",
                "resources": {}
            },
            {
                "hostIP": "192.168.250.10",
                "image": "k8s.gcr.io/kube-proxy:v1.17.5",
                "name": "kube-proxy",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "192.168.250.10",
                "resources": {}
            },
            {
                "hostIP": "192.168.250.10",
                "image": "k8s.gcr.io/kube-scheduler:v1.17.5",
                "name": "kube-scheduler",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "192.168.250.10",
                "resources": {
                    "requests": {
                        "cpu": "100m"
                    }
                }
            },
            {
                "hostIP": "192.168.250.11",
                "image": "k8s.gcr.io/kubernetes-dashboard-amd64:v1.10.1",
                "name": "kubernetes-dashboard",
                "nodeName": "k8s-worker-01",
                "phase": "Running",
                "podIP": "10.44.0.1",
                "resources": {}
            },
            {
                "hostIP": "192.168.250.10",
                "image": "docker.io/weaveworks/weave-kube:2.6.2",
                "name": "weave",
                "nodeName": "k8s-master",
                "phase": "Running",
                "podIP": "192.168.250.10",
                "resources": {
                    "requests": {
                        "cpu": "10m"
                    }
                }
            },
            {
                "hostIP": "192.168.250.11",
                "image": "docker.io/weaveworks/weave-kube:2.6.2",
                "name": "weave",
                "nodeName": "k8s-worker-01",
                "phase": "Running",
                "podIP": "192.168.250.11",
                "resources": {
                    "requests": {
                        "cpu": "10m"
                    }
                }
            },
            {
                "hostIP": "192.168.250.12",
                "image": "docker.io/weaveworks/weave-kube:2.6.2",
                "name": "weave",
                "nodeName": "k8s-worker-02",
                "phase": "Running",
                "podIP": "192.168.250.12",
                "resources": {
                    "requests": {
                        "cpu": "10m"
                    }
                }
            }
        ]
    }
}
```

## Kubernetes Dashboard

As part of the provisioning we have added the Kubernetes Dashboard. Therefore,
in order to get access to it you must perform a few extra things.

### Create Dashboard Service Account

First, create the dashboard service account:

```bash
kubectl create serviceaccount dashboard-admin-sa
```

Next bind the dashboard-admin-service-account service account to the
cluster-admin role:

```bash
kubectl create clusterrolebinding dashboard-admin-sa \
--clusterrole=cluster-admin --serviceaccount=default:dashboard-admin-sa
```

Next we need to obtain the secrets:

```bash
kubectl get secrets
...
NAME                             TYPE                                  DATA   AGE
dashboard-admin-sa-token-lrssx   kubernetes.io/service-account-token   3      23s
default-token-j76qj              kubernetes.io/service-account-token   3      55m
```

Now we need to describe to get the access token:

```bash
kubectl describe secret dashboard-admin-sa-token-lrssx
...
Name:         dashboard-admin-sa-token-lrssx
Namespace:    default
Labels:       <none>
Annotations:  kubernetes.io/service-account.name: dashboard-admin-sa
              kubernetes.io/service-account.uid: e946b610-1097-457e-b06d-af54de62ed06

Type:  kubernetes.io/service-account-token

Data
====
ca.crt:     1025 bytes
namespace:  7 bytes
token:      eyJhbGciOiJSUzI1NiIsImtpZCI6ImRwYTJjMkR6dXFhX3BwLTZweVBUSFFkUThWUHl1TTNQRWdvTEU2MXVHd3MifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJkZWZhdWx0Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6ImRhc2hib2FyZC1hZG1pbi1zYS10b2tlbi1scnNzeCIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50Lm5hbWUiOiJkYXNoYm9hcmQtYWRtaW4tc2EiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiJlOTQ2YjYxMC0xMDk3LTQ1N2UtYjA2ZC1hZjU0ZGU2MmVkMDYiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6ZGVmYXVsdDpkYXNoYm9hcmQtYWRtaW4tc2EifQ.gOykiKGJ0hMwuNi72eHi-4u6Tm66foFHjzcxsN8ObeR6a5WMgD1UM2Qo6vqFA0uCNo1BPGJn5wB56Fm7ABfnSkauMxSeHnh7ZFHca9SV4jKF-M1fjHUEJ80NdZs4IgYM0cFjFXdGk3RFDfUyjbfMjBCQpY3S2kuc9ANd9Pq2PK9HEQT2-5a9ME_ChbiGoFnpdCYVD18Bzmtko-BJBGnKLDQ3-MlF7myEzo_XRiVh1J_mHKUob80VumaQ0nKnVf9HV_saLJqMstf-F-_Ooogf-cyNz8BUCSdIdXfRqhp8-8MdYzwTYgG3IHNRjVVAc3MPsic0XPfsQIZJ49_KLVekiw
```

Copy the token and enter it into the token field on the Kubernetes dashboard login page.

Start the proxy to get access to the dashboard:

```bash
kubectl proxy
```

Open up the [dashboard](http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/) using your browser of choice.
