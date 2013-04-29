# Maintainer: Janne Haapsaari <haaja@iki.fi>
# Contributor: Arun <cute.tec@gmail.com>
# Contributor: Juanma Hernandez <juanmah@gmail.com>

pkgname=gnome-shell-extension-pomodoro
pkgver=0.8
pkgrel=1
pkgdesc="Pomodoro timer extension for gnome-shell"
arch=('any')
url="https://github.com/codito/gnome-shell-pomodoro"
license=('GPL3')
depends=('gnome-shell>=3.8')
optdepends=('gnome-tweak-tool: A tool to customize advanced GNOME 3 options.')
provides=('gnome-shell-extension-pomodoro')
conflicts=('gnome-shell-extension-pomodoro-git')
source=("https://github.com/codito/gnome-shell-pomodoro/zipball/${pkgver}"
        'icon-cache.patch')
md5sums=('94f3560bbb855b3a1b8e859f95dfebc2'
         'cab47246d6791e0faa42ea76a5270cd2')
groups=('gnome-shell-extensions')
install='gschemas.install'

_name="codito-gnome-shell-pomodoro-41534f2"

build() {
    cd ${srcdir}/${_name}
    patch -p0 -i "${srcdir}/icon-cache.patch"
    # for some reason while extracting autogen.sh loses execute rights
    chmod +x ${srcdir}/${_name}/autogen.sh
    ./autogen.sh --prefix=${pkgdir}/usr --disable-schemas-compile
    make
}

package() {
    cd ${srcdir}/${_name}
    gtk-update-icon-cache
    make install
}
