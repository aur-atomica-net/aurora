# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=aurora
pkgver=0.8.0
pkgrel=1
pkgdesc='Fault tolerant job scheduler for Mesos which handles dependencies and ISO8601 based schedules'
arch=('any')
url='http://aurora.apache.org/'
license=('Apache')
depends=('java-runtime' 'java-environment')
makedepends=('gradle')
source=(
  "${pkgname}-${pkgver}.tar.gz"::"https://codeload.github.com/apache/aurora/tar.gz/${pkgver}"
)
sha512sums=('fe08230d5603e6a41b152b84bae5828fc89247203700d49145eeb5c83ef9963b82b6c8d1c0f00b7222e33ff56a40eafff268cd8209243b9e619f44977744e501')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  gradlew wrapper
}

package() {
  install -Dm644 "$pkgname/target/$pkgname-$pkgver.jar" "$pkgdir/usr/share/$pkgname/$pkgname.jar"
}

# vim:set ts=2 sw=2 et:
