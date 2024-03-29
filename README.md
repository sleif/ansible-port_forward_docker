sleif.port_forward_docker
============

This role runs a socat based port forwarding in docker.
Docker image: <https://github.com/manusa/docker-images/tree/master/port-forward>

Requirements
------------

Use it on a machine setup with ansible role sleif.docker.

Role Variables
--------------

- docker_network_name (can be defined in sleif.docker)
- virtual_host (entry point hostname)
- remote_host
- remote_port

Dependencies
------------

Needs sleif.docker to make sure Docker is configured as needed.

Example Playbook
----------------

    - hosts: "server"
      user: root
      vars:
        docker_network_name: 'custom_docker_network'
      roles:
        - { role: sleif.nginx_docker, tags: "nginx_docker",
                                          virtual_host: "external-host.example.com",
                                          remote_host: "target-host.internal.example.com",
                                          remote_port: "8080" }

License
-------

MIT

Author Information
------------------

Created in 2021 by Sebastian Berthold
