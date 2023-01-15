# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt5-glacier-app
pkgver=0.9.2
pkgrel=1
pkgdesc="Glacier Application library"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/libglacierapp"
license=('LGPL-2.0-or-later')
depends=('qt5-declarative>=5.11')
makedepends=('cmake')
provides=('libglacierapp')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('f9a56adf91dc8269727ecb1b89b649b584dafdb9c8695737c031710ba2d20cb8')

build() {
    cd libglacierapp-$pkgver
    mkdir -p build
    cd build
    cmake \
	-DCMAKE_BUILD_TYPE=Release \
	-DCMAKE_INSTALL_PREFIX=/usr \
	-DCMAKE_INSTALL_LIBDIR=lib \
	-DBUILD_EXAMPLES=ON \
	-DCMAKE_VERBOSE_MAKEFILE=ON \
	..
    cmake --build .
}

package() {
    cd libglacierapp-$pkgver
    cd build
    make DESTDIR="$pkgdir/" install
}
