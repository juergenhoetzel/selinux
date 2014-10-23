# Maintainer: Nicolas Iooss (nicolas <dot> iooss <at> m4x <dot> org)
# Contributor: Timothée Ravier <tim@siosm.fr>
# Contributor: Nicky726 (Nicky726 <at> gmail <dot> com)
# Contributor: Sergej Pupykin (pupykin <dot> s+arch <at> gmail <dot> com)

pkgname=sepolgen
pkgver=1.2.1
pkgrel=2
pkgdesc="SELinux policy generator"
groups=('selinux')
arch=('any')
url='http://userspace.selinuxproject.org'
license=('GPL')
depends=('python2')
conflicts=("selinux-usr-${pkgname}")
provides=("selinux-usr-${pkgname}=${pkgver}-${pkgrel}")
source=("https://raw.githubusercontent.com/wiki/SELinuxProject/selinux/files/releases/20140506/${pkgname}-${pkgver}.tar.gz")
sha256sums=('438c246bdc6b3cf1b12116831f4c601aaae6e93decb007dddab212a3c88781b0')

prepare() {
  cd ${pkgname}-${pkgver}
  sed -i -e "s/ python/ python2/" src/sepolgen/Makefile
}

build() {
  cd ${pkgname}-${pkgver}
  make
}

package(){
  cd ${pkgname}-${pkgver}
  make DESTDIR="${pkgdir}" install
}
