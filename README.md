# SHCS
Smart Home Control System

## Hardware description
...Raspberry pi 3 b+
...Elecrow 7 inch, touch screen

## Installing LIRC
http://www.raspberrypiwiki.com/index.php/Raspberry_Pi_IR_Control_Expansion_Board

 sudo apt install lirc

add in /boot/config.txt lines

`dtoverlay=gpio-ir,gpio_pin=18       #(without: in)
 dtoverlay=gpio-ir-tx,gpio_pin=17    #(without: out)`


==============================
## Making Flask as an cron job

[link](https://www.raspberrypi.org/documentation/linux/usage/rc-local.md raspberry docu)

remove apache if you don't need it

 pi@raspi:\~$ sudo apt-get remove apache2

 pi@raspi:\~$ sudo apt autoremove

sudo nano /etc/rc.local

add line befor end command *'exit 0'*:

`python3 /home/pi/webapp/app.py &`

========
## Running chrome in kiosk mode

create directory:

 pi@raspi:\~$ mkdir .config/lxsession/LXDE-pi/

write autostart file:

vim autostart

add line:
`chromium-browser --incognito --noerrdialogs --kiosk http://localhost:5000/`

deactivate maus pointer. add line in *.bash_profile*

`[[ -z $DISPLAY && $XDG_VTNR -eq 1 ]] && startx -- -nocursor`

and just reboot raspi ;)
