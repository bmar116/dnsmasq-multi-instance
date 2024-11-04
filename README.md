# dnsmasq-multi-instance
Running DNSMASQ as a systemd service for multiple instances

## Install
Install into your ``/usr/lib/systemd/system`` folder or wherever your system's ``systemd`` service files are located.

Make sure the ``/var/lib/dnsmasq`` and ``/var/log/dnsmasq`` directories exist. Put your configuration files into the ``/var/lib/dnsmasq/`` directory titled ``<interface>.conf``.

## Run
Run ``systemctl start dnsmasq@<interface>`` to start the service for the relevant ``<interface>``.

## Configuration Files
The option ``interface=`` does not have to be included in your interface's configuration file. The `dnsmasq` service is run with the ``--interface=`` and ``--except-interface=lo --bind-interfaces`` options. All other config options are supported.
