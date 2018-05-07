```html
  ___  ___  ___ _____ _   _
 | _ \/ _ \| _ \_   _/_\ | | of ._ o  
 |  _/ (_) |   / | |/ _ \| |__  |_)|  
 |_|  \___/|_|_\ |_/_/ \_\____| |
```

PORTAL of Pi - RaspberyPi based PORTAL device. Certified UNIX Network Technicians only!

Development and Design Guide
=============================

By: the grugq <thegrugq@gmail.com>

Guide
=====

This will guide you through configuring an Arch based RaspberryPi installation
which transparently forwards all TCP traffic over the Tor network. There is 
also a Tor SOCKS proxy for explicitly interacting with the Tor network, either
for more security, or to access a Hidden Service.

The configuration of access to the Internet is left as an exercise to the reader.

My mods
=======

Uses a wireless AP instead of an ethernet interface to connect to the Pi (More users!). Adapted create_ap instead of using hostapd and dnsmasq directly. Also, all \*.log in /var/log/ point to /dev/null so we don't save any extra info just in case. Social media and insecure IMs are blocked, PORTALofPi was intended to keep your anonymity.

### My personal setup
 * Raspberry Pi Zero W
 * Alfa AWUS036NEH Wireless USB Adapter

For portability a USB charger will be a good idea.

### Notes
 * Change AP password (search for _CHANGEME_ string).
 * AP will be hidden so search for SSID "InPORTAL" or change it to one of your own (Remember that protocol is WPA2).
 * Avoid ads and related on client level:
   * https://github.com/hoshsadiq/adblock-nocoin-list
   * http://support.it-mate.co.uk/downloads/HOSTS.txt
 * Make sure you are prepending `proxychains` before any command that connects to something on the Internet from the device itself (like `curl`).

TODO
====
 - [x] Fix tor service rage quitting because it can't bind to the wlan1 address (create_ap is much slower and systemd is crap).
 
