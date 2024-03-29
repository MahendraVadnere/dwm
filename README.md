# dwm
This is my work-in-progress build of DWM

This dwm is built with Flexipatch (<https://github.com/bakkeby/dwm-flexipatch>) and cleaned up with Flexipatch Finaliser (<https://github.com/bakkeby/flexipatch-finalizer>) so that the config.h files are easier to use.

Patches
-------
This is a heavily patched version of DWM that contains the following patches that I have explcitly enabled:

```
Always Center
Autostart
Status2d
Systray
Restartsig
Movestack
Pertag
Warp
Fullscreen
Fakefullscreen
Placemouse
Resizecorners
Swallow
Viewontag
Bottomstack
Centeredmaster
Vanitygaps
Attachbottom
Statuspadding
Seamlessrestart
```

Instructions for Installation
-----------------------------
* Dependencies

```
xorg
xserver-xorg
libx11-dev
libxinerama-dev
libxft-dev
libxcb1-dev
libx11-xcb-dev
libxcb-res0-dev
xcb
libxcb-xkb-dev
x11-xkb-utils
libxkbcommon-x11-dev
build-essential
gcc
make
```

* To install

```
git clone https://github.com/MahendraVadnere/dwm
cd dwm
make clean install
```
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm

Display/Login Manager Users
---------------------------
For systems having Display Manager or Login Manager (like GDM,
LightDM, LXDM, etc) need not to start DWM through startx and
need not to usr .xinitrc file.

Just add the dwm.desktop file in your systems xsessions
folder (for example, /usr/share/xsessions/)

Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

