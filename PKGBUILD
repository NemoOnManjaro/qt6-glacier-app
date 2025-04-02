# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt6-glacier-app
pkgver=1.0.3
pkgrel=1
pkgdesc="Glacier Application library"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/libglacierapp"
license=('LGPL-2.0-or-later')
depends=('qt6-declarative>=6.0')
makedepends=('cmake')
provides=('libglacierapp')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('0f6c2a5458661e8e31c6680f159afa037063d72540bf2272223dbe1fd2cd5654')

build() {
    cd libglacierapp-$pkgver
    mkdir -p build
    cd build
    cmake \
	-DUSE_QT6:BOOL=true \
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
