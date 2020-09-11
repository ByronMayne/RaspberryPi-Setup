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

## Dnsmasq   
The Pi-hole uses a custom fork of this and if you want to edit to have custom dns routing you can.
`/etc/dnsmasq.d/01-pihole.conf`

## Changing the Admin Port
By default PiHole runs on port 80 for it's admin page. If we are going to setup a reverse proxy this will break so we need to move it.

The port is defined here 

`sudo nano /etc/lighttpd/lighttpd.conf`

However there is a big warning saying how that will be overridden on update so we need to a make a new file and define the port

```sh
sudo nano 
```
and write the following in the file and replace the `{PORT_NUMBER}` with the port you want it to run on
```
server.port := {PORT_NUMBER} 
```
> Make sure you use `:=` otherwise you well get an error about duplicated variables. `:=` says it's okay to override

Then restart the server using 
```sh
sudo /etc/init.d/lighttpd restart
```
