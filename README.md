# ansible-k8s

An [Ansible](https://www.ansible.com) role to deploy a
[Kubernetes](https://kubernetes.io) - K8s Cluster

- [Weave-Net](https://www.weave.works/docs/net/latest/kube-addon/) is used for
  the network overlay currently

## Requirements

Install additional required [Ansible](https://www.ansible.com) roles:

```bash
sudo ansible-galaxy install -r requirements.yml
```

## Role Variables

[defaults/main.yml](defaults/main.yml)

## Dependencies

None

## Example Playbook

[Vagrant/playbook.yml](Vagrant/playbook.yml)

## Vagrant

To spin up a test cluster using Vagrant. Check out the [README](Vagrant/README.md).

## License

MIT

## Author Information

Larry Smith Jr.

- [EverythingShouldBeVirtual](http://everythingshouldbevirtual.com)
- [@mrlesmithjr](https://www.twitter.com/mrlesmithjr)
- <mailto:mrlesmithjr@gmail.com>
