# i3wm

Here I list the requirements to use this i3 config.

# Arch/Manjaro configuration

Most important packages

    $ sudo pacman -S i3-gaps i3status dmenu i3lock xorg-xbacklight feh picom  ttf-font-awesome xfce4-terminal 

Other packages

    $ sudo pacman -S thunar evince flatpak tlp timeshift bitwarden code vim lxsession lxappearance redshift blueman dunst ranger xfce4-screenshooter thunderbird snapd texlive-most

Configuring yay

    $ sudo pacman -S --needed git base-devel
    $ cd /opt
    $ git clone https://aur.archlinux.org/yay.git
    $ sudo chown -R user:user ./yay
    $ cd yay
    $ makepkg -si

Installing yay packages

    $ yay -S j4-dmenu-desktop birdtray brave-bin

Installing flatpak packages (see below to conidfigure flapak)
    
    $ flatpak install skype discord zoom	

Installing snap packages

    $ snap install electronplayer

Switching branches in Manjaro

    $ sudo pacman-mirrors --api --set-branch {branch} #replace {branch} with stable/testing/unstable
    $ sudo pacman-mirrors --fasttrack 5 && sudo pacman -Syyu

# Debian configuration

Most important packages

    $ sudo apt install i3 i3status dmenu i3lock feh j4-dmenu-desktop network-manager-gnome compton fonts-font-awesome xfce4-terminal

Other packages

    $ sudo apt install thunar evince flatpak tlp timeshift vim lxsession lxappearance redshift blueman dunst ranger xfce4-screenshooter

Configuring i3-gaps
    
    #Dependencies
        $ sudo apt install dh-autoreconf libxcb-keysyms1-dev libpango1.0-dev libxcb-util0-dev xcb libxcb1-dev libxcb-icccm4-dev libyajl-dev libev-dev libxcb-xkb-dev libxcb-cursor-dev libxkbcommon-dev libxcb-xinerama0-dev libxkbcommon-x11-dev libstartup-notification0-dev libxcb-randr0-dev libxcb-xrm0 libxcb-xrm-dev libxcb-shape0 libxcb-shape0-dev meson
    
    #Building from source
        # clone the repository
        $ git clone https://www.github.com/Airblader/i3 i3-gaps
        $ cd i3-gaps

    # compile & install
        $ mkdir -p build && cd build
        $ meson ..
        $ ninja
        $ sudo meson install

Namespaces are disabled by default which doesn't allow to run snaps and appimages, to permanentely enable them:

    $ echo 'kernel.unprivileged_userns_clone=1' > /etc/sysctl.d/00-local-userns.conf
    $ service procps restart


# Fedora configuration

Most important packages

    $ sudo dnf install i3 i3status dmenu i3lock feh network-manager-applet picom fontawesome-fonts xfce4-terminal

Other packages

    $ sudo dnf install thunar evince flatpak tlp timeshift vim lxsession lxappearance redshift blueman dunst ranger xfce4-screenshooter

Configuring i3-gaps
    
    #Dependencies

        $ sudo dnf install libxcb-devel xcb-util-keysyms-devel xcb-util-devel xcb-util-wm-devel xcb-util-xrm-devel yajl-devel libXrandr-devel startup-notification-devel libev-devel xcb-util-cursor-devel libXinerama-devel libxkbcommon-devel libxkbcommon-x11-devel pcre-devel pango-devel git gcc automake meson perl-ExtUtils-MenuMaker

    #Building from source
        # clone the repository
        $ git clone https://www.github.com/Airblader/i3 i3-gaps
        $ cd i3-gaps

    # compile & install
        $ mkdir -p build && cd build
        $ meson ..
        $ ninja
        $ sudo meson install

Enabling RPM Fusion
    
    #Free repo
        $ sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm   
    
    #Non-free repo
        $ sudo dnf install https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

# Flatpak configuration

Adding Flathub

    $ sudo flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo

# Dunst configuration
    
    
    $ mkdir ~/.config/dunst
    $ sudo cp ~/dotfiles/dunstrc ~/.config/dunst/dunstrc
    $ sudo chown user:user ~/.config/dunst/dunstrc
