# Omni Bare Metal Provider

[Omni Bare Metal Provider](https://github.com/siderolabs/omni-infra-provider-bare-metal) is a Sidero Omni infrastructure provider that PXE-boots and manages bare-metal machines as Talos Linux nodes.

## Prerequisites

- A running [Sidero Omni](https://omni.siderolabs.com/) instance.
- An Omni InfraProvider service account key (create with `omnictl infraprovider create bare-metal`).
- A DHCP server in the same broadcast domain as the bare-metal machines. This provider runs a DHCP proxy for iPXE boot — it does not replace the DHCP server.
- Reachability to a Talos [Image Factory](https://www.talos.dev/v1.8/learn-more/image-factory/) (defaults to `factory.talos.dev`).
- Either Host Network enabled or the container attached to a docker macvlan/ipvlan that can broadcast on UDP 67 (the DHCP proxy needs L2 access to bare-metal machines).
