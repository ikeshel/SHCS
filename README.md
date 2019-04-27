# SHCS
Smart Home Control System

==============================
## Making Flask as an cron job

[link](https://www.raspberrypi.org/documentation/linux/usage/rc-local.md raspberry docu)

remove apache if you don't need it

`pi@raspi:\~$ sudo apt-get remove apache2

pi@raspi:\~$ sudo apt autoremove`

sudo nano /etc/rc.local

add line befor end command *'exit 0'*:

`python3 /home/pi/webapp/app.py &`

