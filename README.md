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

[wrt54gl]: https://www.linksys.com/us/p/P-WRT54GL/
[dd-wrt]: https://wiki.dd-wrt.com
[firmware]: https://wiki.dd-wrt.com/wiki/index.php/Linksys_WRT54GL#Firmware