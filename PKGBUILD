# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>


pkgname=glacier-calc
pkgver=0.3.3
pkgrel=1
pkgdesc="Nemo calculator"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/glacier-calc"
license=('BSD-3-Clause' 'LGPL-2.1-only')
depends=('qt5-glacier-app-git')
makedepends=('git' 'cmake' 'qt5-tools')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('b2c656a40f5562a08e2f35625f7b4026a2a1ab7055e94ce990dbc9b5fdb213c0')

build() {
    cmake \
        -B "${pkgname}-${pkgver}/build" \
        -S "${pkgname}-${pkgver}" \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr'
    make -C "${pkgname}-${pkgver}/build" all
}

package() {
    make -C "${srcdir}/${pkgname}-${pkgver}/build" DESTDIR="$pkgdir" install
}
