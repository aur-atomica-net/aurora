# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=aurora
_gitname=aurora
pkgver=0.8.0
pkgrel=1
pkgdesc='Fault tolerant job scheduler for Mesos which handles dependencies and ISO8601 based schedules'
arch=('any')
url='http://aurora.apache.org/'
license=('Apache')
depends=('jre8-openjdk')
makedepends=('jdk8-openjdk' 'git' 'python2')
source=("git://git.apache.org/aurora.git")
sha512sums=('SKIP')

build() {
  cd "${srcdir}/${_gitname}"
  unset _JAVA_OPTIONS
  GRADLE_USER_HOME="${srcdir}" ./gradlew assemble
}

pkgver() {
  cd "${srcdir}/${_gitname}"
  echo "0.$(git rev-list --count master).$(git describe --always)"
}

package() {
  install -Dm644 "${srcdir}/${_gitname}/dist/libs/aurora-0.9.0-SNAPSHOT.jar" "${pkgdir}/usr/share/${pkgname}/${pkgname}.jar"
}

# vim:set ts=2 sw=2 et:
