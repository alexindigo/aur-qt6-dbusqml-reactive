# Maintainer: Alex Indigo <ai at aegis dot one>

pkgname=qt6-dbusqml-reactive
_projname=dbusqml
pkgver=0.2.5
pkgrel=1
pkgdesc="Standalone D-Bus binding for QML (no KDE dependencies) — reactive bindings enabled"
arch=('x86_64' 'aarch64')
url="https://github.com/alexindigo/dbusqml"
license=('GPL-3.0-or-later')
depends=('qt6-base' 'qt6-declarative')
makedepends=('cmake')
provides=("qt6-dbusqml=${pkgver}")
conflicts=('qt6-dbusqml' 'qt6-dbusqml-git')
source=("${pkgname}-${pkgver}.tar.gz::${url}/archive/refs/tags/v${pkgver}.tar.gz")
sha256sums=('9d370b084d65f8261fb4088fc2fdeee1cb26bb63a6887336e66399181a2dbad7')

build() {
    cmake -B build -S "${srcdir}/${_projname}-${pkgver}" \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_TEST_MODE=OFF \
        -DDBUSQML_REACTIVE_BINDINGS=ON \
        -DCMAKE_SKIP_RPATH=ON \
        -DCMAKE_INSTALL_PREFIX=/usr
    cmake --build build
}

package() {
    DESTDIR="${pkgdir}" cmake --install build
}
