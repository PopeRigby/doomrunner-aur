# Maintainer:     Cassidy Wilson <cassidywilson at mailbox dot org>	

pkgname=doomrunner
pkgver=1.3.3
pkgrel=1
pkgdesc="A ZDoom launcher using Qt"
arch=('x86_64')
url="https://github.com/Youda008/DoomRunner"
license=('GPL3')
depends=('qt5-base')
makedepends=('git')
source=("git://github.com/qbasicer/qzdl.git")
md5sums=("SKIP")

build()
{
  cd "${srcdir}/${_gitname}"
  git checkout ${_branch}
  rm -rf "${srcdir}/${_gitname}-build"
  mkdir "${srcdir}/${_gitname}-build"
  ls -A | grep -v .git | xargs -d '\n' cp -r -t ../${_gitname}-build
  cd "${srcdir}/${_gitname}-build"
  cmake ../qzdl-build 
  make
}

package()
{
  cd "${srcdir}/${_gitname}-build"
  mkdir -p "${pkgdir}/usr/bin"
  mv "zdl" "${pkgdir}/usr/bin/qzdl"
}

