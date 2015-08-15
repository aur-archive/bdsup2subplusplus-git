# Maintainer: Gustavo Alvarez <sl1pkn07@gmail.com>

pkgname=bdsup2subplusplus-git
pkgver=20130410.7c8af86
pkgrel=1
pkgdesc="Subtitle conversion tool for image based stream formats with scaling capabilities and some other nice features. (GIT version)"
arch=('i686' 'x86_64')
license=('Apache')
url="https://github.com/amichaelt/BDSup2SubPlusPlus"
depends=('libqxt')
makedepends=('git' 'cmake')
provides=('bdsup2subplusplus')
conflicts=('bdsup2subplusplus')
source=('bdsup2subpp.desktop'
        'bdsup2subpp.png'
        'bdsup2subpp::git://github.com/amichaelt/BDSup2SubPlusPlus.git')
md5sums=('0b9aa9997081d7431e87e33c38b5ff48'
         'a557384ef1b5c80c23b3d3762979e30c'
         'SKIP')
_gitname="bdsup2subpp"

pkgver() {
  cd "${_gitname}"
  echo "$(git log -1 --format="%cd" --date=short | tr -d '-').$(git log -1 --format="%h")"
}

build() {
  cd "${_gitname}/src"

  qmake-qt4
  make
}

package() {
  cd "${_gitname}/src"
  install -Dm755 bdsup2sub++ "${pkgdir}/usr/bin/bdsup2subpp"
  install -Dm644 help.htm "${pkgdir}/usr/share/doc/${_gitname}/help.htm"

  install -Dm644 "${srcdir}/bdsup2subpp.desktop" "${pkgdir}/usr/share/applications/bdsup2subpp.desktop"
  install -Dm644 "${srcdir}/bdsup2subpp.png" "${pkgdir}/usr/share/pixmaps/bdsup2subpp.png"
}
