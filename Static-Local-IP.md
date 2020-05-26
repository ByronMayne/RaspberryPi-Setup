# Static IP

## What
Gives you Pi a static unchanging IP address from your router. 

## Why
When accessing your Pi from another computer you will need to know it's IP address. By default when you PI connects to your router it will be assigned an IP address like `192.168.0.100`. This address is only leased out to the PI for a set amount of time. After that point or if you reconnect to the router you will get a new IP. We want that to be unchanging, this is where a static IP comes in.



## Start

1) Open up a terminal window for your Pi and enter in `sudo nano /etc/dhcpcd.conf`
2) Scroll down the the bottom to the following section.

*You edit `eth0` if you want a static wired connection or `wlan0` if you want a static wired connection*
```
interface eth0

static ip_address=192.168.0.10/24
static routers=192.168.0.1
static domain_name_servers=192.168.0.1

interface wlan0

static ip_address=192.168.0.200/24
static routers=192.168.0.1
static domain_name_servers=192.168.0.1
```

3) Updated the following values for `th0` for a static wired connection or `wlan0` for a static wireless connection

**static ip_address**: The would be the address you wanted eg: `192.168.0.100`. Make sure you leave the `/24` at the end. 

**static routers**: This is the IP address of your gateway (probably the IP address or your router

**static domain_name_servers**: This is the IP address of your DNS (probably the IP address of your router). You can add multiple IP addresses here separated with a single space.

4) To exit press `ctrl + x`
5) Press 'Y'. 
6) Restart Pi

> Once the reboot has finished you can check that it worked by typing `ifconfig`.

