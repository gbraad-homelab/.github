Homelab related repositories
============================

This organization contains application repistories for the following:

### [[Nextcloud](https://github.com/gbraad-homelab/personal-nextcloud)]

### [[Forgejo](https://github.com/gbraad-homelab/personal-forgejo)] <span title="Automated build">⚙️</span>

```
$ podman run -d --name forgejo --hostname ${HOSTNAME}-forgejo \
    --net=ncentre-bridge --ip 10.0.21.150 \
    --cap-add=NET_ADMIN --cap-add=NET_RAW --device=/dev/net/tun --cap-add AUDIT_CONTROL \
    ghcr.io/gbraad-homelab/forgejo:latest
```

```
$ bootc switch ghcr.io/gbraad-homelab/forgejo-bootc:latest
```

### [[Jellyfin](https://github.com/gbraad-homelab/personal-jellyfin)]

```
$ podman run -d --name jellyfin --hostname ${HOSTNAME}-jellyfin \
    --net=ncentre-bridge --ip 10.0.21.160  \
    --cap-add=NET_ADMIN --cap-add=NET_RAW --device=/dev/net/tun --cap-add=SYS_ADMIN --device=/dev/fuse \
    ghcr.io/gbraad-homelab/jellyfin:latest
```

```
$ bootc switch ghcr.io/gbraad-homelab/jellyfin-bootc:latest
```


### [[Home Assistant](https://github.com/gbraad-homelab/personal-homeassistant)]

> [!NOTE]
> Instructions to run the image-based deployment can be found here: [Image-based Virtual Machines](https://github.com/gbraad-dotfiles/.github/blob/main/profile/README.md#image-based-virtual-machines)


- ...

using [Tailscale](https://tailscale.com) and [Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/).
This means the applications are exposed to a private and/or public network, without the need for a public IP address.
More network related setup is published at [spotsnel](https://github.com/spotsnel/), such as system containers for Tailscale and Cloudflared

Hosted applications can be found at [gbraad-apps](https://github.com/gbraad-apps/), such as [personal-obsidian](https://github.com/gbraad-apps/personal-obsidian).
