# Maintainer: Voobscout <voobscout+aur@gmail.com>
# Original maintainer: M Rawash <mrawash@gmail.com>
# Contributor: olvar <beren dot olvar (at) gmail dot com>
# Contributor: Andrew Antle <andrew dot antle at gmail dot com>
# Contributor: joyfulgirl <joyfulgirl (at) archlinux.us>
# Contributor: Jonathan Friedman <jonf@gojon.com>

pkgname=xfs
pkgver=1.1.4
pkgrel=1
pkgdesc="X Font Server"
arch=('i686' 'x86_64')
license=('GPL2')
# depends=()
makedepends=('git' 'pkg-config' 'autoconf' 'automake' 'gettext' 'xproto' 'xtrans' 'wget')
url="http://ftp.x.org/pub/individual/app"
provides=('xfs')
# optdepends=()
source=("http://ftp.x.org/pub/individual/app/$pkgname-$pkgver.tar.gz")
sha256sums=('28f89b854d1ff14fa1efa5b408e5e1c4f6a145420310073c4e44705feeb6d23b')
install=xfs.install
options=(!strip)  # Thanks to sidereus for pointing this out

build() {
  msg "GIT checkout done or server timeout"

  cd ${srcdir}/${pkgname}-${pkgver}

  msg "Configuring XFS..."
  ./configure --prefix=/usr

  msg "Compiling XFS... "
  make
}

package() {
  msg "Installing XFS"
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install
}
