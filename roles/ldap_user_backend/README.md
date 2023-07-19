# `finallycoffee.nextcloud.ldap-user-backend` ansible role

Ansible role for managing LDAP authentication of nextcloud instances using ansible.

## Prerequisites

This role assumes a nextcloud instance is up and running, and has the `user_ldap`
nextcloud app installed. For starting a nextcloud instance, see the
`finallycoffee.nextcloud.server` role, for managing nextcloud apps see the
`finallycoffee.nextcloud.apps` ansible role.

## Configuration

- Set `nc_ldap_api_method` to either `occ` or `http` to control wether the
  configuration is set using `php occ` command line calls or the `http` API
  of the `user_ldap` nextcloud app.

- For `nc_ldap_api_method: occ`, ensure `nc_ldap_container` is set to the name
  of the docker container where nextcloud is running, and `nc_ldap_occ_user` is
  the user the container / nextcloud itself runs as. `nc_ldap_occ_command`
  _can_ also be tweaked if `php` is not in the path, but the default should
  be fine in most cases.

- For `nc_ldap_api_method: http`, ensure `nc_ldapi_api_instance_url` contains
  the URL to the nextcloud server, including protocol (and port, if
  non-standard), and `nc_ldap_api_basic_auth_[user|password]` contain the
  credentials of an admin user with the rights to edit the LDAP settings.

- Set `nc_ldap_test_configuration` to `true`/`false` to have the role issue a
  nextcloud-provided test of the configured LDAP configuration, this corresponds
  to a `occ ldap:test-config <id>`.

For most of the options, see the
[nextcloud manual on configuration keys](https://docs.nextcloud.com/server/latest/admin_manual/configuration_user/user_auth_ldap_api.html#configuration-keys),
the config keys are mapped 1:1 with a prefix of `nc_ldap_config_` and
the so-called "snake-case" (`ldap_backup_host`), so `ldapUserFilterMode` becomes
`nc_ldap_config_ldap_user_filter_mode`.
