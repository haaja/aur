gnome-shell-extension-pomodoro
==============================

Arch Linux PKGBUILD for
[gnome-shell-extension-pomodoro](https://github.com/codito/gnome-shell-pomodoro).

Building package
----------------

1. Clone the repository

    git clone git://github.com/haaja/gnome-shell-extension-pomodoro.git

2. Build the package

    makepkg

3. Install package

    sudo pacman -U gnome-shell-extension-pomodoro-0.7-1-any.pkg.tar.xz

4. Reload gnome-shell

    Alt+F2 and r

5. Enable extension using `gnome-tweak-tool` or

    gsettings get org.gnome.shell enabled-extensions

    gsettings set org.gnome.shell enabled-extensions [<values from get above>, pomodoro@arun.codito.in]
