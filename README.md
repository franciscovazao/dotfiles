# i3wm

Here I list the requirements to use this i3 config.

# Manjaro configuration

Most important packages

    $ sudo pacman -S i3 i3status dmenu i3lock xorg-xbacklight feh picom j4-dmenu-desktop

Other packages

    $ sudo pacman -S brave thunar evince flatpak tlp timeshift bitwarden code timeshift vim xfce4-terminal lxsession lxappearance ttf-font-awesome

Configuring flatpak and yay

    $ sudo flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
    $ sudo pacman -S --needed git base-devel
    $ cd /opt
    $ git clone https://aur.archlinux.org/yay.git
    $ sudo chown -R user:user ./yay-git
    $ cd yay-git
    $ makepkg -si


# Debian configuration

Most important packages

    $ sudo apt install i3 i3status dmenu i3lock xorg-xbacklight feh picom j4-dmenu-desktop network-manager-gnome

Other packages

    $ sudo apt install thunar evince flatpak tlp timeshift vim xfce4-terminal lxsession lxappearance ttf-font-awesome

Configuring i3-gaps
    
    #Dependencies

        $ apt install dh-autoreconf libxcb-keysyms1-dev libpango1.0-dev libxcb-util0-dev xcb libxcb1-dev libxcb-icccm4-dev libyajl-dev libev-dev libxcb-xkb-dev libxcb-cursor-dev libxkbcommon-dev libxcb-xinerama0-dev libxkbcommon-x11-dev libstartup-notification0-dev libxcb-randr0-dev libxcb-xrm0 libxcb-xrm-dev libxcb-shape0 libxcb-shape0-dev meson
    
    #Building from source
        # clone the repository
        $git clone https://www.github.com/Airblader/i3 i3-gaps
        $cd i3-gaps

    # compile & install
        $ mkdir -p build && cd build
        $ meson ..
        $ ninja
        $ meson install



