# $Id$
# Contributor: TheKit <nekit1000 at gmail.com>
# Contributor: Bart Ribbers <bribbers@disroot.org>
# Contributor: Alexey Andreyev <aa13q@ya.ru>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=qt5-glacier-app
pkgver=0.9
pkgrel=2
pkgdesc="Glacier Application library"
arch=('x86_64' 'aarch64')
url="https://github.com/nemomobile-ux/libglacierapp"
license=('LGPL-2.0-or-later')
depends=('qt5-declarative>=5.11')
makedepends=('cmake')
provides=('libglacierapp')
source=("${url}/archive/refs/tags/$pkgver.tar.gz")
sha256sums=('f3d0dd7b505ad86b9e7b57c39de190158f0dd0566ff772d596b84e263d4395b2')

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
