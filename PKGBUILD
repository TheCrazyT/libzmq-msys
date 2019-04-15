pkgname=libzmq
pkgver=4.3.1
pkgrel=2
pkgdesc=""
arch=('x86_64')
url="http://www.zeromq.org"
license=("GPL3")
depends=("cmake")
source=(https://github.com/zeromq/libzmq/releases/download/v${pkgver}/zeromq-${pkgver}.tar.gz)
sha256sums=('bcbabe1e2c7d0eec4ed612e10b94b112dd5f06fcefa994a0c79a45d835cd21eb')

prepare() {
  cd "${srcdir}/zeromq-${pkgver}/"
}

build() {
  if [ ! -d "${srcdir}/zeromq-${pkgver}/build" ]
  then
	mkdir "${srcdir}/zeromq-${pkgver}/build"
  fi
  cd "${srcdir}/zeromq-${pkgver}/build"

  cmake -DZMQ_HAVE_WINDOWS=0 ..
}


package() {
  cd "${srcdir}/zeromq-${pkgver}/build"
  make DESTDIR="${pkgdir}" install
}
