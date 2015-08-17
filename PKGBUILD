# Contributor: giacomogiorgianni@gmail.com>

pkgname=wxpdfdoc
pkgver=0.9.3
pkgrel=1
pkgdesc="wxPdfDocument allows wxWidgets applications to generate PDF documents."
url="http://sourceforge.net/projects/wxcode/files/Components/wxPdfDocument/"
arch=('i686' 'x86_64')
license=('GPL')
depends=('wxgtk')
makedepends=('autoconf' 'intltool' 'gettext')
source=(http://sourceforge.net/projects/wxcode/files/Components/wxPdfDocument/$pkgname-$pkgver.tar.gz)
md5sums=('0c853fdf7ad19f936431b15e679c0361')

build() {
  cd "${srcdir}/$pkgname-$pkgver"
  cd build
  ./acregen.sh
  cd ..
  ./configure --prefix=/usr
  make all
}

package() {
  cd "${srcdir}/$pkgname-$pkgver"
  make DESTDIR=${pkgdir} install
  install -dm755 $pkgdir/usr/include/wx/pdfdc/samples
  cp -r ${srcdir}/$pkgname-$pkgver/samples ${pkgdir}/usr/include/wx/pdfdc/
}
