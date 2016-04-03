# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=aurora
pkgver=0.12.0
pkgrel=1
pkgdesc='Fault tolerant job scheduler for Mesos which handles dependencies and ISO8601 based schedules'
arch=('any')
url='http://aurora.apache.org/'
license=('Apache')
depends=('jre8-openjdk')
makedepends=('jdk8-openjdk' 'git' 'python2')
source=("http://apache.claz.org/aurora/${pkgver}/apache-aurora-${pkgver}.tar.gz")
sha256sums=('682e953237811d4fb0c94a08fd027c967de637be4260a32c19ee1e77c0f930e9')

build() {
  cd "${srcdir}/${_gitname}"
  unset _JAVA_OPTIONS
  GRADLE_USER_HOME="${srcdir}" ./gradlew assemble
}

package() {
  install -Dm644 "${srcdir}/${_gitname}/dist/libs/aurora-${pkgver}.jar" "${pkgdir}/usr/share/${pkgname}/${pkgname}.jar"
}

# vim:set ts=2 sw=2 et:
