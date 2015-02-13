# Maintainer: Voobscout <voobscout+aur@gmail.com>
pkgname=xorg-xfs
pkgver=1.1.4
pkgrel=1
pkgdesc="X Font Server"
arch=('i686' 'x86_64')
license=('GPL2')
makedepends=('git' 'pkg-config' 'autoconf' 'automake' 'gettext' 'xproto' 'xtrans' 'wget')
url="http://ftp.x.org/pub/individual/app"
provides=('xorg-xfs')
source=("http://ftp.x.org/pub/individual/app/xfs-1.1.4.tar.gz")
sha256sums=('28f89b854d1ff14fa1efa5b408e5e1c4f6a145420310073c4e44705feeb6d23b')
install=xfs.install
options=(!strip)

build() {
  cd ${srcdir}/xfs-1.1.4
  msg "Configuring XFS..."
  ./configure --prefix=/usr
  msg "Compiling XFS... "
  make
}

package() {
  msg "Installing XFS"
  cd ${srcdir}/xfs-1.1.4
  make DESTDIR=${pkgdir} install
}
# vim:set ts=2 sw=2 et:
