# Tutorial to display anything you want on your ram

## Purpose

My ram had no built in color cycles, so i created them myself (+displayed my servers status in it).


## Requirements & Disclaimers

In this tutorial, i'll show how to display anything on your rgb devices using [openRGB](https://openrgb.org).

I'll be using the build in openRGB CLI. You will need to ***fully install openRGB*** before beeing able to follow this tuto.

Do note that i'll be using ***python VENV*** in my project, but you can just ignore it and download the libraries without using venv if you want.

As we will be using python and libraries, you will need to create ***PYTHON VENV***, so be sure that everything is set up.

This step by step guide will be covered on ***LINUX*** only, as i will use a lot of ***SYSTEMD***'s features. Good luck for windows users lol.

Do note that playing with your ram display can completly mess it's display up, so do be carefull when your injecting instructions !!!!!





# GUIDE

There is surely some more efficient or covinient methods to make it works, but it still works fine the way i did it. Feel free to adapt, or suggest anything.

## openRGB' server startup

Once openRGB is installed, you will gotta be sure that it is always running, even when you restart your server.

**Be sure that 'openrgb' can be used as an environnement variable !!!**

running ``openrgb status`` in cmd should be working.


- Go into systemd files

``cd /etc/systemd/system``

- Create a systemd service called ``ram-rgb-manager.service`` (or whatever you want, till it has .service at the end)

- Edit the content

<pre>
[Unit]
Description=OpenRGB Server startup and python ram-manager startup
After=network.target

[Service]
ExecStart=/path/to/project/openrgb-ram-manager-startup.sh
Type=simple

User=Your_user

[Install]
WantedBy=multi-user.target
</pre>

In ``[Service]`` put your user name and change the path of the .sh file.

- TODO (edit openrgb start up file)

TODO : Copy all files in simplified form and remove absolute path (left to modify)