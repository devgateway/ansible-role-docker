# devgateway.docker

Install Docker.

## Optional Variables

### `dkr_packages`

Dictionary of lists of packages to install, keys are `ansible_os_family`.

Default:

* **RedHat**: ['firewalld', 'docker', 'python-docker-py']
* **Debian**: ['firewalld', 'docker.io', 'python3-docker']


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

