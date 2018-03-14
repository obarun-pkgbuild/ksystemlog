# $Id$
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Maintainer: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=ksystemlog
pkgver=17.12.3
pkgrel=3
pkgdesc='System log viewer tool'
url='https://kde.org/applications/system/ksystemlog/'
arch=(x86_64)
license=(GPL LGPL FDL)
groups=(kde-applications kdeadmin)
depends=(kio)
makedepends=(extra-cmake-modules kdoctools python)
conflicts=(kdeadmin-ksystemlog)
replaces=(kdeadmin-ksystemlog)
source=("https://download.kde.org/stable/applications/$pkgver/src/$pkgname-$pkgver.tar.xz")
sha256sums=('991203b77c322f7a56f73b2ae381c3b57ebc9c913b5dc0a98898f681796cd252')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DBUILD_TESTING=OFF \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
