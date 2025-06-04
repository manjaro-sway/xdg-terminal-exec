# Maintainer: Max Gautier <mg@max.gautier.name>
pkgname=xdg-terminal-exec
pkgver=0.12.4
pkgrel=1
pkgdesc="Proposed standard to launching desktop apps with Terminal=true"
arch=(any)
url="https://gitlab.freedesktop.org/Vladimir-csp/$pkgname"
makedepends=('scdoc')
checkdepends=('bats')
license=('GPL-3.0-or-later')
source=("${pkgname}-${pkgver}::$url/-/archive/v${pkgver}/${pkgname}-v${pkgver}.tar.gz")
sha256sums=('525c241267a3b2a5f94199216df7e68938c49654f59edb3e54a94207f379658c')
b2sums=('2a0e43b93113982880ac85faf9daeaeaa803d822cbe70d6f70fa5d646c07dca79a03074292c854c88acd507bb6803bc554756858bca983c26cca9aa5eeea6fd6')

check() {
    cd "$pkgname-v$pkgver"
    bats "test/"
}

build() {
    make -C "$pkgname-v$pkgver"
}

package() {
    make -C "$pkgname-v$pkgver" prefix="$pkgdir/usr" install
}
