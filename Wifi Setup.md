# Wifi Setup


## Getting your network information

Every time you see this network name and password in the guide you need to change them to the network name and password of your local network.

If you need to find the network name of your local network you can run the following command in the Raspberry terminal:

`sudo iwlist wlan0 scan`

This will list all the networks in your vicinity along with some useful information for each network. To find your network name look for something that look like: ESSID:”Test Wifi Network”.

## Configuring your WiFi network

To tell the Raspberry Pi to automatically connect to your WiFi network you need to edit a file called: wpa_supplicant.conf.

To open the file in nano type the following command:

`sudo nano /etc/wpa_supplicant/wpa_supplicant.conf`

Scroll to the end of the file and add the following to the file to configure your network:

```
network={
   ssid="WifiNetwork"
   psk="Password"
}
```

Save and close the file by pressing **Ctrl+X** followed by **Y**. At this point the Raspberry Pi should automatically connect to your network.
