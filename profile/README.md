Homelab related repositories
============================

Instructions to run the image-based deployment can be found here: [Image-based Virtual Machines](https://github.com/gbraad-dotfiles/.github/blob/main/profile/README.md#image-based-virtual-machines)

This organization contains application repistories for the following:


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


### [[Jellyfin](https://github.com/gbraad-homelab/personal-jellyfin)] <span title="Automated build">⚙️</span>

```
$ podman run -d --name jellyfin --hostname ${HOSTNAME}-jellyfin \
    --net=ncentre-bridge --ip 10.0.21.160  \
    --cap-add=NET_ADMIN --cap-add=NET_RAW --device=/dev/net/tun --cap-add=SYS_ADMIN --device=/dev/fuse \
    ghcr.io/gbraad-homelab/jellyfin:latest
```

```
$ bootc switch ghcr.io/gbraad-homelab/jellyfin-bootc:latest
```


### [[Nextcloud](https://github.com/gbraad-homelab/personal-nextcloud)] <span title="Automated build">⚙️</span>

```
$ podman run -d --name nextcloud --hostname ${HOSTNAME}-nextcloud \
    --net=ncentre-bridge --ip 10.0.21.130  \
    --cap-add=NET_ADMIN --cap-add=NET_RAW --device=/dev/net/tun \
    -v /var/lib/nextcloud:/var/lib/nextcloud \
    ghcr.io/gbraad-homelab/nextcloud:latest
```

```
$ wget https://github.com/gbraad-homelab/personal-nextcloud/releases/download/250223/disk.qcow2 \
     -O nextcloud.qcow2
$ sudo virt-install \
    --name nextcloud --os-variant fedora-eln \
    --cpu host --vcpus 4 --memory 4096 \
    --import --disk ./nextcloud.qcow2,format=qcow2
```

> [!NOTE]
> At the moment `bootc switch` will not work for this image due to the content in `/var` and `/etc`.


### [[Home Assistant](https://github.com/gbraad-homelab/personal-homeassistant)] <span title="Automated build">⚙️</span>

```
$ podman run -d --name homeassistant --hostname ${HOSTNAME}-homeassistant \
    --net=nroute-switch --ip 10.0.21.90 \
    --cap-add=NET_ADMIN --cap-add=NET_RAW --device=/dev/net/tun \
    ghcr.io/gbraad-homelab/homeassistant:latest
```

```
$ wget https://github.com/gbraad-homelab/personal-homeassistant/releases/download/250223/disk.qcow2 \
     -O homeassistant.qcow2
$ sudo virt-install \
    --name homeassistant --os-variant fedora-eln \
    --cpu host --vcpus 4 --memory 4096 \
    --import --disk ./nextcloud.qcow2,format=qcow2
```

> [!NOTE]
> At the moment `bootc switch` will not work for this image due to the content in `/var` and `/etc`.


- ...

using [Tailscale](https://tailscale.com) and [Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/).
This means the applications are exposed to a private and/or public network, without the need for a public IP address.
More network related setup is published at [spotsnel](https://github.com/spotsnel/), such as system containers for Tailscale and Cloudflared

Hosted applications can be found at [gbraad-apps](https://github.com/gbraad-apps/), such as [personal-obsidian](https://github.com/gbraad-apps/personal-obsidian).
