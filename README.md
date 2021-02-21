sleif.port_forward_docker
============

This role runs a socat based port forwarding in docker.

Requirements
------------

Use it on a machine setup with ansible role sleif.docker.

Role Variables
--------------

- DOCKER_NETWORK_NAME (can be defined in sleif.docker)
- VIRTUAL_HOST (entry point hostname)
- REMOTE_HOST
- REMOTE_PORT

Dependencies
------------

Needs sleif.docker to make sure Docker is configured as needed.

Example Playbook
----------------

    - hosts: "server"
      user: root
      vars:
        DOCKER_NETWORK_NAME: 'custom_docker_network'
      roles:
        - { role: sleif.nginx_docker, tags: "nginx_docker",
                                          VIRTUAL_HOST: "external-host.example.com",
                                          REMOTE_HOST: "target-host.internal.excample.com",
                                          REMOTE_PORT: "8080" }

License
-------

MIT

Author Information
------------------

Created in 2021 by Sebastian Berthold
