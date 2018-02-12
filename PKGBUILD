# $Id$
# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Maintainer: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=ksystemlog
pkgver=17.12.2
pkgrel=2
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
sha256sums=('31b1b7eac1330d1a18806759a96f131a2de1aaf5ad160d3fc623eab167a881ab')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DBUILD_TESTING=OFF \
    -DCMAKE_INSTALL_PREFIX=/usr
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
