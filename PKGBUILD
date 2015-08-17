# Maintainer: Jerome Leclanche <jerome@leclan.ch>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Pier Luigi Fiorini <pierluigi.fiorini@gmail.com>

_pkgname=qt5-systems
pkgname=$_pkgname-git
pkgver=v5.0.0.beta1.109.gee755a7
pkgrel=2
pkgdesc="A cross-platform application and UI framework (QtSystems)"
arch=("i686" "x86_64")
url="https://qt-project.org/"
license=("LGPL")
depends=("qt5-declarative" "gconf")
makedepends=("git")
provides=("$_pkgname")
conflicts=("$_pkgname")
source=("$_pkgname::git+https://gitorious.org/qt/qtsystems.git#branch=dev")
sha256sums=("SKIP")

pkgver() {
	cd "$srcdir/$_pkgname"
	git describe --always | sed "s/-/./g"
}

prepare() {
	mkdir -p build
	cd build
	qmake "$srcdir/$_pkgname"
	make
}

package() {
	cd build
	make INSTALL_ROOT="$pkgdir" install
}
