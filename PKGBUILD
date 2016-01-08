# Maintainer: Adrian Piotrowicz <nexces+chakraos@nxstudio.pl>
 
pkgname=vagrant-deb
pkgver=1.7.4
pkgrel=2
pkgdesc="Vagrant from official DEB package. Version 1.7.4"
arch=(i686 x86_64)
url="http://www.vagrantup.com/"
license=('MIT')
depends=()
makedepends=('binutils')
optdepends=('virtualbox: default VM provider')
provides=('vagrant')
conflicts=('vagrant' 'vagrant-git')
replaces=('vagrant')
options=(!strip staticlibs)
source=(https://releases.hashicorp.com/vagrant/${pkgver}/vagrant_${pkgver}_x86_64.deb)
sha256sums=('dcd2c2b5d7ae2183d82b8b363979901474ba8d2006410576ada89d7fa7668336')
 
prepare() {
	cd "$srcdir"
	ar p vagrant_${pkgver}_x86_64.deb control.tar.gz | tar xzf -
	ar p vagrant_${pkgver}_x86_64.deb data.tar.gz | tar xzf -
}
 
check() {
	cd "$srcdir"
	md5sum -c md5sums || return 1
}
 
package() {
	cd "$srcdir"
	mv opt "$pkgdir/"
	mv usr "$pkgdir/"
}