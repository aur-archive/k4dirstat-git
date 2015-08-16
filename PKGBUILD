# Maintainer: Tom Debruyne <tomdebruyne at gmail dot com>
# Contributor: Jerome Leclanche <jerome.leclanche+arch@gmail.com>

pkgname=k4dirstat-git
_gitname="k4dirstat"
pkgver=2.7.5.r0.g1ad2e96
pkgrel=1
pkgdesc="A graphical disk usage utility for KDE (KDE4 port)"
arch=('i686' 'x86_64')
url=('https://bitbucket.org/jeromerobert/k4dirstat')
license=('GPL')
depends=('kdebase-lib>=4.5')
makedepends=('docbook-xsl' 'automoc4' 'git' 'cmake')
provides=('k4dirstat')
conflicts=('k4dirstat')
source=("git+https://bitbucket.org/jeromerobert/k4dirstat.git")
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_gitname"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}
build() {
cd "$srcdir/$_gitname"
cmake -DCMAKE_INSTALL_PREFIX=`kde4-config --prefix`
make
}
package() {
cd "$srcdir/$_gitname"
make DESTDIR="$pkgdir/" install
install -Dm644 COPYING "$pkgdir"/usr/share/licenses/k4dirstat/LICENSE
}
