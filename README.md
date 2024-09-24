# `finallycoffee.nextcloud` ansible collection

## Overview

This ansible collection provides various roles for deploying
and managing nextcloud installations

## Roles

- [`server`](roles/server/README.md): For deploying
  and configuring a bare nextcloud instance in a docker container.
  Supports both the `-apache` (default) and `-fpm` variants.
- [`apps`](roles/apps/README.md):
  For managing nextcloud apps in an already installed nextcloud
  server instance. Can install, remove, enable/disable and update apps.
- [`ldap_user_backend`](roles/ldap_user_backend/README.md):
  Manages LDAP authentication sources in installed nextcloud instances.
- [`nginx_fpm_proxy`](roles/nginx_fpm_proxy/README.md):
  Reverse proxy role which connects to nextcloud using FPM
  and serves static content.

## License

[CNPLv7+](LICENSE.md): Cooperative Nonviolent Public License
