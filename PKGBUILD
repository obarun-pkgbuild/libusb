# Maintainer: Eric Vidal <eric@obarun.org>
# based on the original https://projects.archlinux.org/svntogit/packages.git/tree/trunk/PKGBUILD?h=packages/libusb
# 						Maintainer:  Bartłomiej Piotrowski <bpiotrowski@archlinux.org>
# 						Contributor: Tobias Powalowski <tpowa@archlinux.org>

pkgname=libusb
pkgver=1.0.22
pkgrel=2
pkgdesc='Library that provides generic access to USB devices'
arch=(x86_64)
url='http://libusb.info/'
license=('LGPL')
depends=('glibc')
replaces=('libusb1' 'libusbx')
provides=("libusbx=$pkgver" libusb-1.0.so)
conflicts=('libusbx')
source=(https://github.com/libusb/libusb/releases/download/v$pkgver/libusb-$pkgver.tar.bz2)
md5sums=('466267889daead47674df933cea9cacb')
validpgpkeys=('6DD4217456569BA711566AC7F06E8FDE7B45DAAC') # Eric Vidal

build() {
  cd ${pkgname}-$pkgver
  ./configure --prefix=/usr 
  make
}

check() {
  make -C ${pkgname}-$pkgver check
}

package () {
  make -C ${pkgname}-$pkgver DESTDIR="$pkgdir" install
}
