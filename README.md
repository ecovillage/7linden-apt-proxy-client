# 7linden-apt-proxy-client

Create a .deb package suitable for \*buntu, Debian, Linux Mint.

## /opt/7linden-apt-proxy-client/bin/apt-proxy-client

Script checks whether we are at home (by using 7linden-at-home methodology or looking at dhcp search domain).

If we are, (apt-) proxy configuration is read from `/etc/7linden/apt-proxy.conf` and a respective file in `/etc/apt/apt.conf.d/` is created, by default `/etc/apt/apt.conf.d/01proxy`.

The package installs an ifup-script so that above mentioned script is always executed after the network interface is brought up.

Note that the script should have no file-ending such that it can be linked in `/etc/network/if-up.d/` and thus be called at bootup time with `ifup -a`.

This can be done with `sudo ln -s /opt/7linden-apt-proxy-client/bin/apt-proxy-client /etc/network/if-up.d/apt-proxy-client`.
This is also wrapped in two scripts:

  /opt/7linden-apt-proxy-client/bin/install_ifup_script

and

  /opt/7linden-apt-proxy-client/bin/uninstall_ifup_script

which do just that - and the first is executed at package installation time.

### Package building

To build the package you need to have [FPM](https://github.com/jordansissel/fpm) in the path and execute `create.sh`.  packages version number is taken from the `VERSION` file.

### License

Copyright 2016, Holger Nassenstein.

Released under the [GPLv3](LICENSE) (or any later) as included as LICENSE file.

### Contribute

You are welcome, drop us a line and issue a Pull Request.

