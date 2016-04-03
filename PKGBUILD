# Maintainer: Jason R. McNeil <jason@jasonrm.net>

pkgname=aurora
pkgver=0.12.0
pkgrel=1
pkgdesc='Fault tolerant job scheduler for Mesos which handles dependencies and ISO8601 based schedules'
arch=('any')
url='http://aurora.apache.org/'
license=('Apache')
depends=('java-environment>=8')
makedepends=('java-environment>=8' 'git' 'python2')
source=("git+https://github.com/apache/aurora.git")
sha256sums=('SKIP')

build() {
    cd "${srcdir}/${pkgname}"
    git checkout rel/${pkgver}
    unset _JAVA_OPTIONS
    export GRADLE_USER_HOME="${srcdir}"
    ./gradlew distTar
}

package() {
    install -d "${pkgdir}/opt/${pkgname}"
    tar xf "${srcdir}/${pkgname}/dist/distributions/aurora-scheduler-${pkgver}.tar" --strip-components=1 -C "${pkgdir}/opt/${pkgname}"
    rm "${pkgdir}/opt/${pkgname}/bin/aurora-scheduler.bat"

    install -d "${pkgdir}/usr/bin"
    cd "${pkgdir}/usr/bin"
    ln -s "/opt/${pkgname}/bin/aurora-scheduler" aurora-scheduler
}
