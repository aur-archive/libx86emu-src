pkgname=libx86emu-src
pkgver=1.1.23.1
pkgrel=1
pkgdesc='x86 emulation library'
arch=('x86_64' 'i686' 'armv7h')
url='http://download.opensuse.org/source/factory/repo/oss/suse/src/'
license=('BSD')
depends=('glibc')
makedepends=('make' 'gcc')
conflicts=('libx86emu')
source=("http://download.opensuse.org/source/factory/repo/oss/suse/src/libx86emu-${pkgver%.*.*}-${pkgver#*.*.}.src.rpm")
sha256sums=('2073552362c81bf4e47c20ce8f0f2038641b6f790a2740eb745e284ff44eef10')

prepare() {
  tar jxf "libx86emu-${pkgver%.*.*}.tar.bz2"
}

build() {
  make -C "libx86emu-${pkgver%.*.*}" LIBDIR=/usr/lib
}

package() {
  make -C "libx86emu-${pkgver%.*.*}" LIBDIR=/usr/lib DESTDIR="$pkgdir" install
  install -Dm644 "libx86emu-${pkgver%.*.*}/LICENSE" \
    "$pkgdir/usr/share/licenses/libx86emu/LICENSE"
}

