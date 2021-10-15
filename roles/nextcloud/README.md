# `finallycoffee.nextcloud.nextcloud` ansible role

This role can be used to deploy nextcloud in a docker container,
regardless of wether the `apache` or `fpm` docker image is used.

It provides various common (optimization) configuration options
and creates a user on the host which is mapped into the container,
so the host file permissions remain comprehensible.
