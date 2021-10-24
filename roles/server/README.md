# `finallycoffee.nextcloud.nextcloud` ansible role

This role can be used to deploy nextcloud in a docker container,
regardless of wether the `apache` or `fpm` docker image is used.

It provides various common (optimization) configuration options
and creates a user on the host which is mapped into the container,
so the host file permissions remain comprehensible.

## Configuration

- `nextcloud_socket_path`: Setting this (to, for example, `{{ nextcloud_basepath }}/socket`),
  will make FPM listen on `{{ nextcloud_socket_path }}/nextcloud.sock` on the host, enabling
  you to use FPM to interface with nextcloud.
