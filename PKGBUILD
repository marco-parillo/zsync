pkgname=zsync
pkgver=0.6.2
pkgrel=1
pkgdesc="A file transfer program that's able to connect to rsync servers"
arch=("x86_64")
url="http://zsync.moria.org.uk/"
depends=("glibc")
license=("custom:Artistic")
source=(http://${pkgname}.moria.org.uk/download/${pkgname}-${pkgver}.tar.bz2)
sha512sums=('56437594831f2320c532759805b5c51116c53c8848f14b54cfd9b76676d1d061abe7fc914264f496ed1c7922fbbd5b884166c855a2fb9eb1285f216e478c5f0d')

build() {
  cd "${srcdir}"/${pkgname}-${pkgver}

  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}"/${pkgname}-${pkgver}

  make prefix="${pkgdir}"/usr install
  install -d "$pkgdir/usr/share/licenses/$pkgname"
  mv "$pkgdir/usr/share/doc/zsync/COPYING" "$pkgdir/usr/share/licenses/$pkgname/"
}
