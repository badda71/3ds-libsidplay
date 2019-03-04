pkgname=3ds-libsidplay
pkgver=1.36.60
pkgrel=1.0
pkgdesc="SID chip music module playing library"
arch=('any')
url="https://github.com/badda71/3ds-libsidplay"
license=('GPLv2')
options=(!strip libtool staticlibs)
source=(
	"${url}/raw/master/libsidplay-${pkgver}.tar.gz"
	"${url}/raw/master/libsidplay-${pkgver}.patch"
)
makedepends=('3ds-pkg-config' 'devkitpro-pkgbuild-helpers' 'patch')
groups=('3ds-portlibs')

build() {
  cd libsidplay-$pkgver
  patch -p0 -i ../libsidplay-${pkgver}.patch
  source /opt/devkitpro/3dsvars.sh
  ./configure --prefix="${PORTLIBS_PREFIX}" --host=arm-none-eabi --target=arm-none-eabi --disable-shared --enable-static
  make
}

package() {
  cd libsidplay-$pkgver
  source /opt/devkitpro/3dsvars.sh
  make DESTDIR="$pkgdir" install
}