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

* Wallpaper 
* 
Before we do anything else. I like to have a nice wallpaper to look at while configuring the rest of my installation.
I am very fond of the Facet Wallpapers that can be found here http://imgur.com/a/k83u0.
Pick one you like and download it. Gnome Desktop makes it easy for us to change the wallpaper. Just right-click the desktop and click Change Background.

## Terminal Enviroment

### Terminal Emulator

The thing I usually configure first on a new linux installation is the terminal. The terminal is our home, so
might as well make it livable as soon as possible. By default, bundled with our Evo/Lution install is Xterm.
In itself a pretty configurable terminal emulator, but by god is it sluggish and heavy to use. My terminal of choice is Terminator, because this is the terminal I'm most proficient with. I've been recommended URXTV very very often, but I will stick to Terminator for now.

* Install Terminator

    sudo pacman -S terminator
    
* Disable terminal beep

You might've noticed, if you've been exploring your new installation in the terminal that when backspacing or autocompleting a horrifying beep is sounded. This can become very annoying very quickly and I do not know why this is enabled by default. It is very easy to disable this.

    sudo touch /etc/modprobe.d/disable_sound
    sudo echo "blacklist pcspkr" >> /etc/modprobe.d/disable_sound

The above commands first create a file "disable_sound" in the modprobe.d folder, and then appends "blacklist pcspkr" to the file, which disables the pc-speaker module that causes the problem. This change is automatically loaded on startup.

* Basic Terminator configuration

Now, Terminator is really butt-ugly by default. Before we get to the font-settings and color schemes, let's take a look at the settings pane in Terminator. Right click the Terminator window and click Preferences.

I like disabling the title-bar under Profiles/General options, as well as enabling infinite scrollback and disable the scrollbar under Profiles/Scrolling options.

#### Terminator tips and tricks

* Clear screen with Ctrl+L. 
    
* Start of line is Ctrl+A (nifty if you forget sudo in front of a command)

* End of line is Ctrl+E

### Terminal Shell

By default, our shell is Bash. Here it's all up to personal preference, but I can't recommend ZSH enough. With superior tab-completion and a lot of nifty commands and shortcuts ZSH has quickly become a favorite of mine.

