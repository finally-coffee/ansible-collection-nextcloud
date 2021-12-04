# `finallycoffee.nextcloud` ansible collection

## Overview

This ansible collection provides various roles for deploying
and managing nextcloud installations

## Roles

- [`roles/server`](roles/server/README.md): For deploying
  and configuring a bare nextcloud instance in a docker container.
  Supports both the `-apache` (default) and `-fpm` variants.
- [`roles/apps`](roles/apps/README.md):
  For managing nextcloud apps in an already installed nextcloud
  server instance. Can install, remove, enable/disable and update apps.
- [`roles/ldap-user-backend`](roles/ldap-user-backend/README.md):
  Manages LDAP authentication sources in installed nextcloud instances.
- [`roles/nginx-fpm-proxy`](roles/nginx-fpm-proxy/README.md):
  Reverse proxy role which connects to nextcloud using FPM
  and serves static content.

## License

[CNPLv7+](LICENSE.md): Cooperative Nonviolent Public License
