# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>


pkgname=glacier-calc
pkgver=0.3.4
pkgrel=1
pkgdesc="Nemo calculator"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/glacier-calc"
license=('BSD-3-Clause' 'LGPL-2.1-only')
depends=('qt5-glacier-app>=0.9')
makedepends=('cmake' 'qt5-tools')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('7e973f17e436c05961dc42898528db38ee812bce339f6fca07715ce696f62abe')

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
