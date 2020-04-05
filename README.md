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


[wrt54gl]: https://www.linksys.com/us/p/P-WRT54GL/
[dd-wrt]: https://wiki.dd-wrt.com
[firmware]: https://wiki.dd-wrt.com/wiki/index.php/Linksys_WRT54GL#Firmware