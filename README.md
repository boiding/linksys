# linksys
Notes on how to setup the router

## Router
![The Linksys WRT54GL Wifi router](https://www.linksys.com/images/productmt/834028/372.jpg)

We have a [Linksys WRT54GL][wrt54gl] WiFi router. The hardware revision is `WRT54GL v1.1`.

## Firmware
We will be using [DD-WRT][dd-wrt] as router software. Take a look on their [wiki][firmware] for more information on flashing the firmware.
Remember the router username and password

## Controlling Access
### Setting SSID
Instead of the default SSID, we would like to set the SSID that people associate with the workshop.

To change it go over to `Wireless > Basic Settings` and change the _Wireless Network Name (SSID)_ to **boiding_workshop**.

### Setting Password
The password for access to the network can be set at `Wireless > Security`. The security mode should be set to _WPA2 Personal_.
The _WPA Algorithms_ can be set to TKIP, and the _WPA Shared Key_ to **2boid||!2boid**.

## Static IP-address
In order easily connect with the workshop server, we should give it a static IP-address.

You can look up the MAC address on Linux systems with the following command

```
cat /sys/class/net/*/address
```

Cross-referencing this with the connected devices on the router. The next command is `hostname`, which will provide you with the necessary information.

In the router, go over to `Services > Services`. In the DHCP server section add a static lease with the corresponding MAC address and hostname. Our goto IP-address is `192.168.1.101`

## Number of Leases
A healthy maximum number of teams is 20. It is not unlikely that each team will connect 4 devices, getting a total of 80 connected devices. So we are going to set the maximum number of DHCP users to 100.

Go to `Setup > Basic Setup` and in the section _Network Address Server Settings_ set the _Maximum DHCP Users_ to `100`.

## Open Port 
For the participants server will reach out to the workshop server on port `2643`, which spells *boid* on a phone keypad. We therefor should allow traffic on that port

```
sudo ufw allow 2643
```

[wrt54gl]: https://www.linksys.com/us/p/P-WRT54GL/
[dd-wrt]: https://wiki.dd-wrt.com
[firmware]: https://wiki.dd-wrt.com/wiki/index.php/Linksys_WRT54GL#Firmware
