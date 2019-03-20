# devgateway.docker

Install Docker, and set up `daemon.json`.

## Optional Variables

All variables are dictionaries, keys are `ansible_os_family`.

### `dkr_config_path`

Path to `daemon.json`.

Default: `/etc/docker/daemon.json`

### `dkr_daemon_config`

Dictionary to [recursively
combine](https://docs.ansible.com/ansible/latest/user_guide/playbooks_filters.html#combining-hashes-dictionaries)
with current Docker settings.

Default:

* **RedHat**: {"log-driver": "journald", "selinux-enabled": true, "signature-verification": false}
* **Debian**: {"log-driver": "journald"}

### `dkr_packages`

Packages to install.

Default:

* **RedHat**: ['docker', 'python-docker-py']
* **Debian**: ['docker.io', 'python3-docker']

## Playbook Example

    ---
    - name: Install Docker
      hosts: docker
      tasks:
        - name: Install Docker
          include_role:
            name: devgateway.docker


## License

GPL3+

## Author Information

Copyright 2019, Development Gateway

