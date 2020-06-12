# traefik Ansible role

![](https://github.com/nemonik/traefik-role/workflows/Basic%20role%20syntax%20check/badge.svg)

An Ansible role for ensuring the configuration of a [traefik](https://containo.us/traefik/).

## Requirements

Requires Kubernetes and metallb installed.

## Role Variables

| Variable                | Required | Default               | Choices             | Comments                                         |
|-------------------------|----------|-----------------------|---------------------|--------------------------------------------------|
| traefik_version         | yes      | 1.7.24                | matches release tag | metallb version to install                       |
| traefik_http_port       | yes      | 80                    | Integer             | configures http port                             |
| traefik_admin_port      | yes      | 8080                  | Integer             | configures admin port                            |
| traefik_host            | yes      | 192.168.0.200         | private ip address  | configures ip address for traefik                |
| images_cache_path       | no       | /vagrant/cache/images | Path                | Path to folder used to cache saved Docker images |

## Example Playbook

An example can be found used in my Hands-on DevOps course's [master-playbook.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/ansible/master-playbook.yml).

```
- hosts: masters
  remote_user: vagrant
  roles:
    - common
    - k3s-server
    - metallb
    - traefik
```

The above Ansible playbook uses my ([K3s-server-role](https://github.com/nemonik/k3s-server-role)) to install Lightweight Kubernetes (K3s) and my ([metallb-role](https://github.com/nemonik/metallb-role)).

For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>
