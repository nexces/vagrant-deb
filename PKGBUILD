# Maintainer: Adrian Piotrowicz <nexces+chakraos@nxstudio.pl>
 
pkgname=vagrant-deb
pkgver=1.8.1
pkgrel=1
pkgdesc="Vagrant from official DEB package. Version 1.8.1"
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
sha256sums=('ed0e1ae0f35aecd47e0b3dfb486a230984a08ceda3b371486add4d42714a693d')
 
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