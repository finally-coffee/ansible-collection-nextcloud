# `finallycoffee.nextcloud.nextcloud-apps` ansible role

This role can be used to install/update, remove, enable and disable
nextcloud apps.

## Examples

```yaml
nextcloud_apps:
  # Install cospend app
  - name: cospend
    state: present
  # Make sure mail app is installed, but not enabled
  - name: mail
    state: present
    enabled: no
  # Uninstall photos app
  - name: photos
    state: absent
  # Make sure federation app is always up-to-date
  - name: federation
    state: latest
```
