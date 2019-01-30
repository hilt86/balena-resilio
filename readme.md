### Dockerized Resilio Sync on RPI3

This repo is used with balena.io's excellent IoT container platform. I created this to create a Resilio Sync based NAS with a Raspberry Pi3 and a USB hard drive. To get this working :

1. Sign up for a Balena account
2. Create a RPI3 application
3. Clone this repo
4. Add the balena git repo
5. Format your hard drive as ext4 (or customise systemd mount file)
6. ``git push balena master``
7. Grab the device Ip from Balena dashboard and visit http://deviceip:8888/
