#Maintainer Erik Inkinen <erik.inkinen@gmail.com>
pkgname=libwspcodec
provides=('libwspcodec')
_pkgbase=libwspcodec
pkgver=28.c50f49c
pkgrel=1
arch=('armv7h' 'aarch64' 'x86' 'x86_64')
url="https://github.com/sailfishos/libwspcodec"
license=('GPL2')
depends=()
makedepends=('git' 'pkgconfig' 'glib2')
source=("libwspcodec::git+https://github.com/sailfishos/libwspcodec.git")
md5sums=('SKIP')
options=(debug !strip)

pkgver() {
  cd "${srcdir}/${_pkgbase}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib KEEP_SYMBOLS=1 release pkgconfig
}

package() {
  cd "${srcdir}/${_pkgbase}"
  make LIBDIR=/usr/lib DESTDIR="$pkgdir/" install-dev
}

