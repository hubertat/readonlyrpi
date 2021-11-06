# readonlyrpi
My custom script for making raspberry pi os (buster) readonly.

Based on:
https://hallard.me/raspberry-pi-read-only/
https://gitlab.com/larsfp/rpi-readonly/

Ntp sync issue:
* Added `ntp` and `ntpdate`
* `ntp.service` with `PrivateTmp=false`

Tricks for certain apps:
* Apache2, edit logpath in /etc/apache2/env
* Chromium-browser, use --user-data-dir /tmp/something
* Lightdm - fixed via setup.sh
* Rpi-Cam-Web-Interface: mount /var/www/html/media/ on tmpfs or external rw disk

Usage after setup:
* If you need to change anything, run rw to remount file system read/write. Then ro to make it read only.
* Logs can be read with the command readlog and readlog -f.
