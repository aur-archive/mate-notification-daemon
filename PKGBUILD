# Maintainer : Martin Wimpress <code@flexion.org>
# Contributor: Giovanni Ricciardi <kar98k.sniper@gmail.com>
# Contributor: Xpander <xpander0@gmail.com>

pkgname=mate-notification-daemon
pkgver=1.6.1
pkgrel=3
pkgdesc="Notification daemon for MATE"
url="http://mate-desktop.org"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL' 'LGPL')
depends=('dconf' 'dbus-glib' 'gtk2' 'libcanberra' 'libmatewnck' 'libnotify')
makedepends=('mate-common' 'perl-xml-parser')
options=('!emptydirs')
groups=('mate')
provides=('notification-daemon')
source=("http://pub.mate-desktop.org/releases/1.6/${pkgname}-${pkgver}.tar.xz")
sha1sums=('b911efdc4e37dc0b521165168fee03889f776c12')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname} \
        --disable-static
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
