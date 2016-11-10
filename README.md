# 7linden-apt-proxy-client

Create a .deb package suitable for \*buntu, Debian, Linux Mint.

## /opt/7linden-apt-proxy-client/bin/apt-proxy-client

Script checks whether we are at home (by grepping 7 Linden network name in /etc/resolv.conf).

Note that the script should have no file-ending such that it can be linked in `/etc/network/if-up.d/` and thus be called at bootup time with `ifup -a`.

This can be done with `sudo ln -s /etc/network/if-up.d/apt-proxy-client /opt/7linden-apt-proxy-client/bin/apt-proxy-client`.
This is also wrapped in two scripts:

  /opt/7linden-apt-proxy-client/bin/install_ifup_script

and

  /opt/7linden-apt-proxy-client/bin/uninstall_ifup_script

which do just that.

### Package building

To build the package you need to have [FPM](https://github.com/jordansissel/fpm) in the path and execute `create.sh`.  packages version number is taken from the `VERSION` file.

### License

Copyright 2016, Holger Nassenstein.

Released under the [GPLv3](LICENSE) included as LICENSE file.

### Contribute

You are welcome, drop us a line and issue a Pull Request.

