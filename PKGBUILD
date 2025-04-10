# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>


pkgname=glacier-calc
pkgver=0.4.1
pkgrel=1
pkgdesc="Nemo calculator"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/glacier-calc"
license=('BSD-3-Clause' 'LGPL-2.1-only')
depends=('qt6-glacier-app>=1.0')
makedepends=('cmake' 'qt6-tools' 'clang')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('41b521a191d889f23742cdd028680e9f904f21699e90d7b5a9de7254bb43b667')

build() {
    cmake \
        -B "${pkgname}-${pkgver}/build" \
        -S "${pkgname}-${pkgver}" \
        -DCMAKE_POLICY_VERSION_MINIMUM=3.5 \
        -DCMAKE_INSTALL_PREFIX:PATH='/usr'
    make -C "${pkgname}-${pkgver}/build" all
}

package() {
    make -C "${srcdir}/${pkgname}-${pkgver}/build" DESTDIR="$pkgdir" install
}
