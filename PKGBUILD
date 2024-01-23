# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>


pkgname=glacier-calc
pkgver=0.4
pkgrel=1
pkgdesc="Nemo calculator"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/glacier-calc"
license=('BSD-3-Clause' 'LGPL-2.1-only')
depends=('qt6-glacier-app>=1.0')
makedepends=('cmake' 'qt6-tools')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('6ca4ecf78a28e8d2fd29a37d35796679ca5a98bf400584542e6d46fd2ae7c04c')

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
