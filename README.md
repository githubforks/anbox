# Debian package for Anbox

Packages are only built for Debian 9 (stretch) with amd64 architecture. If you want packages for other distribution or architecture, you can build them from source.

Package source(not the upstream source):

* https://github.com/zhsj/anbox
* https://github.com/zhsj/dbus-cpp
* https://github.com/zhsj/process-cpp
* https://github.com/zhsj/properties-cpp

# Disclaim

These packages are unofficial. If you want support from the Anbox developers, you should follow the official guide on [anbox.io](https://anbox.io) and use snappy to install Anbox.

# Install

First install deb packages.

* sudo wget -O /etc/apt/trusted.gpg.d/zhsj.gpg https://ftp.ustclug.org/~zsj/anbox/zhsj.gpg
* echo "deb [arch=amd64] https://ftp.ustclug.org/~zsj/anbox stretch main" |sudo tee /etc/apt/sources.list.d/anbox.list
* sudo apt update && sudo apt install anbox

Now you need to download the Android image.

* sudo wget -O /var/lib/anbox/android.img https://build.anbox.io/android-images/2017/07/07/android_2_amd64.img

# Start

There are two systemd services.

* sudo systemctl start anbox-container-manager.service
* systemctl --user start anbox-session-manager.service

Now you can start anbox application from your desktop.

If you want these services to start when booting, just

* sudo systemctl enable anbox-container-manager.service
* systemctl --user enable anbox-session-manager.service
