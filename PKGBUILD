# Maintainer: Petros Angelatos <petrosagg@resin.io>
# Based on work by:
#    Calimero <calimerotekni@free.fr>

buildarch=18

pkgname=aufs3-util
pkgver=20130907
pkgrel=1
_gitbranch=aufs3.9
pkgdesc='Necessary utilities for aufs'
arch=('arm armv6h')
url='http://aufs.sourceforge.net/'
license=('GPL2')
makedepends=('aufs3')
replaces=('aufs2-util')
source=("${pkgname}-${_gitbranch}.tar.gz::https://codeload.github.com/morfoh/aufs-util/tar.gz/${_gitbranch}")
md5sums=('85a3440972e16c13a3797bd8a2135fc8')

build() {
	cd "${srcdir}/aufs-util-${_gitbranch}"
	make
}

package() {
	cd "${srcdir}/aufs-util-${_gitbranch}"
	make DESTDIR="${pkgdir}" install

	#fixes for the archlinux /usr/bin move
	mv "${pkgdir}"/sbin/* "${pkgdir}"/usr/bin/
	rmdir "${pkgdir}"/sbin
}
