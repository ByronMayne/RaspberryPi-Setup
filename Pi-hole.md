# Pi-hole
1. Run `curl -sSL https://install.pi-hole.net | bash`
2. Open the following ports
```
sudo ufw allow 80/tcp
sudo ufw allow 53/tcp
sudo ufw allow 53/udp
sudo ufw allow 67/tcp
sudo ufw allow 67/udp
```
3. Set static ip address in the pi or the router
4. Set the DNS lookup to the address on the pi

# Dnsmasq   
The Pi-hole uses a custom fork of this and if you want to edit to have custom dns routing you can.
`/etc/dnsmasq.d/01-pihole.conf`
