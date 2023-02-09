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

### Redis over UNIX-Socket

Set `REDIS_HOST` to a path in the container where the socket is mapped using
`nextcloud_container_extra_environment`. Also set `REDIS_HOST_PORT` to 0
explicitely, as `redis.config.php` will set it to `null` otherwise, resulting
in an exception. Set your redis password in `REDIS_HOST_PASSWORD`.
