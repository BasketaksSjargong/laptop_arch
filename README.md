Laptop - ArchLinux
===========

This github repository is going to be contineously updated as I keep working on my
archlinux installation. All dotfiles, config files and relevant explanations will be included.

## Base installation

For my base installation, I have decided to go with the Evo/Lution live Arch-installer. Hardcore archers might find this a bit cheaty, but I like it for it's ease of use. I've decided to run with the Gnome+Extras window manager. Had I gone with a tiling window manager, my tiler of choice would be the i3-wm. I might do a separate guide on i3.

Motivation behind using Gnome+Extras is the easy-to-configure default Gnome network manager, as well as any barebone essentials already installed. Many people criticize Gnome for it's lack of configurability, and I do see where that come from, but for all intents and purposes Gnome will do just fine. 

* Download Evo/Lution ISO

The Evo/Lution ISO can be downloaded from http://www.evolutionlinux.com/. Proceed by burning it to DVD or a bootable USB device and boot into it on restart.

* Installation

Proceed with the installation as prompted. Chosing Gnome+Extras as your window manager when asked.
When done, reboot the computer and boot into the new ArchLinux installation. Congratulations!

## Terminal Emulator

The thing I usually configure first on a new linux installation is the terminal. The terminal is our home, so
might as well make it livable as soon as possible. By default, bundled with our Evo/Lution install is Xterm.
In itself a pretty configurable terminal emulator, but by god is it sluggish and heavy to use. My terminal of choice is Terminator, because this is the terminal I'm most proficient with. I've been recommended URXTV very very often, but I will stick to Terminator for now.

* Disable terminal beep

You might've noticed, if you've been exploring your new installation in the terminal that when backspacing or autocompleting a horrifying beep is sounded. This can become very annoying very quickly and I do not know why this is enabled by default. It is very easy to disable this.

    sudo touch /etc/modprobe.d/disable_sound
    sudo echo "blacklist pcspkr" >> /etc/modprobe.d/disable_sound





