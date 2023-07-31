# [Docker](#docker)

Install and configure Docker CE on your system.

## [Requirements](#requirements)

None

## [Role Variables](#role-variables)

| Name | Description | Default |
| --- | --- | --- |
| docker_daemon_options | Docker daemon options as a dictionary | `{}` |
| docker_users | A list of users to be added to the docker user group | `[]` |
| docker_version | The version of docker to install | `latest` |

## [Dependencies](#dependencies)

None

## [Example Playbook](#example-playbook)

Install docker 23.0.0 and add vagrant as a docker user.

```yaml
---
- name: Install docker and add vagrant as a docker user
  hosts: all
  roles:
    - role: ajxb.docker
      docker_version: "23.0.0"
      docker_users:
        - vagrant
```

Install docker 23.0.0, add vagrant as a docker user, and configure some docker daemon settings.

```yaml
---
- name: Install docker and add vagrant as a docker user
  hosts: all
  roles:
    - role: ajxb.docker
      docker_version: "23.0.0"
      docker_daemon_options:
        dns:
          - 10.200.10.10
        registry-mirrors:
          - https://docker.mydomain.com
      docker_users:
        - vagrant
```

Install the latest version of docker.

```yaml
---
- name: Install docker
  hosts: all
  roles:
    - role: ajxb.docker
```

## [License](#license)

[Apache-2.0](LICENSE)
