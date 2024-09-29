# `finallycoffee.nextcloud.oidc_user_backend` ansible role

Configure OIDC user backends in nextcloud using this ansible role.
This role can be run multiple times with different arguments in order to
configure multiple oidc-based user backends.

## Configuration

Set `oidc_user_backend_provider_identifier` to a unique identifier.
Populate your provider information in the `oidc_user_backend_config_provider_provider_(settings_)`
like this:

```yaml
oidc_user_backend_config_provider_identifier: my_provider
oidc_user_backend_config_provider_discovery_endpoint: https://idp.example.com/
oidc_user_backend_config_provider_client_id: my-client-id
oidc_user_backend_config_provider_client_secret: my-client-secret

# All options to the occ command are avaible in the
# `oidc_user_backend_config_provider_settings_` namespace
oidc_user_backend_config_provider_settings_unique_id: true
oidc_user_backend_config_provider_settings_send_id_token_hint: true
oidc_user_backend_config_provider_settings_mapping_display_name: name
oidc_user_backend_config_provider_settings_mapping_uid: preferred_username
oidc_user_backend_config_provider_settings_mapping_email: email
```
