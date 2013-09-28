gnome-shell-extension-remove-accessibility-icon
===============================================

Arch Linux PKGBUILD for
[gnome-shell-extension-remove-accessibility-icon](https://github.com/lomegor/Remove-Accessibility).

Building package
----------------

1. Clone the repository

    git clone git://github.com/haaja/gnome-shell-extension-remove-accessibility-git.git

2. Build the package

    makepkg

3. Install package

    sudo pacman -U gnome-shell-extension-remove-accessibility-icon-git-20130330-1-any.pkg.tar.xz

4. Reload gnome-shell

    Alt+F2 and r

5. Enable extension using `gnome-tweak-tool` or

    gsettings get org.gnome.shell enabled-extensions

    gsettings set org.gnome.shell enabled-extensions [<values from get above> removeaccesibility@lomegor]
