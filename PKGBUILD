# Maintainer: Fortunato Ventre (voRia) <vorione AT gmail DOT com>

pkgname=plug-hg
pkgver=124.ec138d96e8c3
pkgrel=1
pkgdesc="Linux software for Fender Mustang amplifiers - Development version"
arch=('i686' 'x86_64')
url="http://piorekf.org/plug/"
license=('GPL3')
depends=('qt4' 'libusb')
makedepends=('mercurial')
provides=('plug')
conflicts=('plug')
source=("hg+https://bitbucket.org/piorekf/plug")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/plug/plug"

  echo $(hg identify -n).$(hg identify -i)
}

build() {
  cd "$srcdir/plug/plug"

  qmake-qt4 target.path=/usr/bin plug.pro
  make
}

package() {
  cd "$srcdir/plug/plug"

  make INSTALL_ROOT="$pkgdir" install
  mkdir -p "$pkgdir/usr/share/doc/plug/"
  cp LICENSE "$pkgdir/usr/share/doc/plug/"
  cp README "$pkgdir/usr/share/doc/plug/"
  rm -r "$pkgdir/usr/local/"
}

# vim:set ts=2 sw=2 et:
