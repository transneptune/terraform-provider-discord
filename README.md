# Discord Terraform Provider

Provides Terraform resources and data sources for managing a Discord server.

This is a fork of [Chaotic-Logic/terraform-provider-discord](https://github.com/Chaotic-Logic/terraform-provider-discord), and a fork of [aequasi/terraform-provider-discord](https://github.com/aequasi/terraform-provider-discord) in turn. The major changes in this fork are:

* The removal of `position` arguments on channel and role types.
* Roles with no permissions are created correctly, without needing a second `terraform apply` to converge their permissions.

This release is **not** API-compatible with either `aequasi/discord` or `Chaotic-Logic/discord`, due to the removal of the position arguments from several types. There is no recommended migration path at this time. If you need positioning and can adjust for the issues around this interface, please use one of those two providers.

## Building the provider

### Development

```sh
go mod vendor
make
```

### Release

```
go mod vendor
export GPG_FINGERPRINT="041C2A19346C00F408CB225BF272BD904C9CF8F5"
goreleaser release --skip-publish
```

## Resources

* discord_category_channel
* discord_channel_permission
* discord_invite
* discord_member_roles
* discord_message
* discord_role
* discord_role_everyone
* discord_server
* discord_text_channel
* discord_voice_channel
* discord_news_channel

## Data

* discord_color
* discord_local_image
* discord_member
* discord_permission
* discord_role
* discord_server
