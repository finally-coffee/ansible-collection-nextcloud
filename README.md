# `finallycoffee.nextcloud` ansible collection

## Overview

This ansible collection provides various roles for deploying
and managing nextcloud installations

## Roles

- [`roles/nextcloud`](roles/nextcloud/README.md): For deploying
  and configuring a bare nextcloud instance in a docker container.
  Supports both the `-apache` (default) and `-fpm` variants.
- [`roles/nextcloud-apps`](roles/nextcloud-apps/README.md):
  For managing nextcloud apps in an already installed nextcloud
  instance. Can install, remove, enable/disable and update apps.

## License

[CNPLv7+](LICENSE.md): Cooperative Nonviolent Public License
