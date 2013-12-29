# Maintainer: Janne Haapsaari <haaja@iki.fi>
# Contributors: Christopher Krooß <didi2002 at web.de>
pkgname="gnome-shell-extension-dash-to-dock"
pkgver="v25"
pkgrel=1
pkgdesc="Transform the dash into an intellihide dock"
arch=('any')
url="https://github.com/micheleg/dash-to-dock/"
license=('GPL')
makedepends=('git' 'gnome-common' 'intltool')
conflicts=('gnome-shell-extensions-git')
_gitroot="https://github.com/micheleg/dash-to-dock.git"
_gitname="dash-to-dock"

build() {
	cd "$srcdir"
	if [ -d $_gitname ] ; then
            cd $_gitname && git pull origin
	else
            git clone $_gitroot
	fi
        git checkout extensions.gnome.org-${pkgver}
	cd "$srcdir/$_gitname"
	sed -i 's/INSTALLBASE = ~\/.local\/share\/gnome-shell\/extensions/INSTALLBASE = ${DESTDIR}/' Makefile 
	make
}

package() {
	cd "$srcdir/$_gitname"
	mkdir -p "${pkgdir}/usr/share/gnome-shell/extensions" "${pkgdir}/usr/share/glib-2.0/schemas/"
	make DESTDIR=${pkgdir}/usr/share/gnome-shell/extensions install
	install -m644 "schemas/org.gnome.shell.extensions.dash-to-dock.gschema.xml" "${pkgdir}/usr/share/glib-2.0/schemas/org.gnome.shell.extensions.dash-to-dock.gschema.xml"
}
