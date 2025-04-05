# WireGuard installer

**This project is a bash script that aims to setup a [WireGuard](https://www.wireguard.com/) VPN on a Linux server, as easily as possible!**

WireGuard is a point-to-point VPN that can be used in different ways. Here, we mean a VPN as in: the client will forward all its traffic through an encrypted tunnel to the server.
The server will apply NAT to the client's traffic so it will appear as if the client is browsing the web with the server's IP.

The script supports both IPv4 and IPv6.

## Requirements

Supported distributions:

- AlmaLinux >= 8
- Alpine Linux
- Arch Linux
- CentOS Stream >= 8
- Debian >= 10
- Fedora >= 32
- Oracle Linux
- Rocky Linux >= 8
- Ubuntu >= 18.04

## Usage

1. Download the latest binary file with the command:

```bash
version=$(curl -s "https://api.github.com/repos/ongtungduong/wireguard-install/releases/latest" | grep '"tag_name":' | sed -E 's/.*"([^"]+)".*/\1/')
curl -LO https://github.com/ongtungduong/wireguard-install/releases/download/$version/wireguard-ctl
```

2. Make the binary file executable.

```bash
chmod +x ./wireguard-ctl
```

3. Move the binary file in to your PATH.

```bash
sudo mv ./wireguard-ctl /usr/local/bin/wireguard-ctl
```

Now you can use the `wireguard-ctl` command to install WireGuard (kernel module and tools) on the server, add or remove clients and get the client configuration file.
