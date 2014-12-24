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

By default, our shell is Bash. Here it's all up to personal preference, but I can't recommend ZSH enough. With superior tab-completion and a lot of nifty commands and shortcuts ZSH has quickly become a favorite of mine. We're going to be using Oh-My-Zsh as a baseline framework for our shell configuration. Oh-My-Zsh is just a bundle of good out of the box plugins and themes.

* Install Zsh and Oh-My-Zsh

First we need to install the shell itself.

    sudo pacman -S zsh
    
We then install Oh-My-Zsh using the program Curl to download the installation script, and piping it directly into our shell.

    curl -L http://install.ohmyz.sh | sh
    
We now need to set ZSH to our default shell. We do this with the following command

    chsh -s /bin/zsh
    
### Terminal color scheme

I'm very fond of dark color schemes. For this installation I am going to go with the scheme Spacegray. This is a color scheme designed for use with Vim, and we'll get back to that later, but we'll also use this as our theme in Terminator.

* Enable 256-color support in terminal

By default, our terminal only supports 8 colors. You can see how many colors your terminal currently supports by running the command

    tput colors

In my case it returns 8.
We want this be 256, otherwise a lot of color schemes that are based on 256 colors are going to look funky. Luckily, most modern terminal emulators support 256 colors.

In our .zshrc file we want to add the line

    # Enable 256 color support
    export TERM="xterm-256color"
    
Now, just restart Terminator and run

    tput colors
    
again. It now returns 256. 

* Download spacegray.terminator

Download spacegray.terminator from https://github.com/ajh17/Spacegray.vim/blob/master/spacegray.terminator.
Now, this is a complete terminator config file. We want to copy its contents to ~/.config/terminator/config and overwrite whatever settings are there. This is going to overwrite some settings. So we're going to have to enter the Terminator settings we changed earlier once again. You might also notice that the font size and shape has changed. This is all personal preference, but I chose to move it back to default for now by ticking "Use the system fixed width font" and "Allow bold text" again.

![Image](https://github.com/BasketaksSjargong/laptop_arch/blob/master/screenshots/Spacegray_terminal_installed.png)





