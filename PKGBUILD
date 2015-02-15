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
source=("http://ftp.x.org/pub/individual/app/xfs-$pkgver.tar.gz"
        "xfs.config"
        "xfs.service"
       )
sha256sums=('28f89b854d1ff14fa1efa5b408e5e1c4f6a145420310073c4e44705feeb6d23b'
            '4b015ad016b2859ec3bf478e67c607078d7b7160d3d4c078e2963f253a7eb9f3'
            '601d447a583fe50ab9a64f6a46c5d85f572ff74917080c0ade2d3192b8f943e1'
           )
install=xfs.install
options=(!strip)

build() {
  cd ${srcdir}/xfs-${pkgver}
  msg "Configuring XFS..."
  ./configure --prefix=/usr
  msg "Compiling XFS... "
  make
}

package() {
  msg "Installing XFS"
  cd ${srcdir}/xfs-${pkgver}
  make DESTDIR=${pkgdir} install

  msg2 "Installing systemd xfs unit"
  install -Dm 0644 ${srcdir}/xfs.service ${pkgdir}/usr/lib/systemd/system/xfs.service
  msg2 "Installing xfs default config"
  install -Dm 0644 ${srcdir}/xfs.config ${pkgdir}/etc/default/xfs
}
# vim:set ts=2 sw=2 et:
