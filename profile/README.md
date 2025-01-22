Homelab related repositories
============================

This organization contains application repistories for the following:
- base infrastructure image for [image-based](https://github.com/gbraad-homelab/private-base) deployment of
  - [Nextcloud](https://github.com/gbraad-homelab/personal-nextcloud)
  - [Forgejo](https://github.com/gbraad-homelab/personal-forgejo)
  - [Jellyfin](https://github.com/gbraad-homelab/personal-jellyfin)
  - [Home Assistant](https://github.com/gbraad-homelab/personal-homeassistant)
- ...

using [Tailscale](https://tailscale.com) and [Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/).
This means the applications are exposed to a private and/or public network, without the need for a public IP address.
More network related setup is published at [spotsnel](https://github.com/spotsnel/), such as system containers for Tailscale and Cloudflared

Hosted applications can be found at [gbraad-apps](https://github.com/gbraad-apps/), such as [personal-obsidian](https://github.com/gbraad-apps/personal-obsidian).
