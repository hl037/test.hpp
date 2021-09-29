# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname="hl037-test"
pkgver="1.0"
pkgrel=1
epoch=
pkgdesc="A halper header to set up parameterized Catch 2 tests"
arch=("any")
url="https://github.com/hl037/test.hpp"
license=('MIT')
groups=()
depends=("catch2")
makedepends=()
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=()
noextract=()
md5sums=()
validpgpkeys=()

package() {
  mkdir -p "${pkgdir}"/usr/include
  echo start : ${startdir} > l
  cp -r ${startdir}/include/hl037 "${pkgdir}"/usr/include
}
