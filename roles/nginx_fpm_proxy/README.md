# `finallycoffee.nextcloud.nginx-fpm-proxy` ansible role

Ansible role for serving nextcloud static content and connecting to dynamic content via PHP-FPM.

## Prerequisites

A running nextcloud instance with FPM available either via IP+port or a unix socket.

## Configuration

- Set `nextcloud_nginx_data_path` to the data directory of the nextcloud instance,
  from where static content etc is served from.

- `nextcloud_nginx_storage_path` needs to be set to the storage path of the nextcloud
  instance, where user data is stored. Usually this is `{{ nextcloud_nginx_data_path }}/data`.

- Set `nextcloud_nginx_fpm_socket_dir` to the directory containing the FPM socket,
  called `nextcloud.sock` by default. This can be overridden in `nextcloud_nginx_fpm_socket_path`.

- If FPM is not used via a unix socket, set `nextcloud_nginx_fpm_server_ip` and
  `nextcloud_nginx_fpm_server_port` accordingly. Note that the IP must be reachable
  from inside the nginx container.
