Very simple script to setup 1 wireguard interfacce (named wg0) with 1 subnet and all clients' traffic routed through VPN server.
Also it depends on iptables and apt, so Debian/Ubuntu is needed (or close derivatives)
If you want to edit script use tabs for indentation, not spaces. Otherwise it'd break `cat <<-EOF`. Or you need to rewrite those parts to avoid leading spaces.

```
apt update && apt install iptables wireguard wireguard-tools sqlite3
wget https://raw.githubusercontent.com/MagoBuono/wgctl/main/wgctl -O /usr/local/bin/wgctl
chmod +x /usr/local/bin/wgctl
wgctl init
wgctl create user1
```
If you have qrencode installed script will also generate QR alongside with client's config on screen.
