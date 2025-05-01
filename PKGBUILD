# Maintainer: Max Gautier <mg@max.gautier.name>
pkgname=xdg-terminal-exec
pkgver=0.12.3
pkgrel=1
pkgdesc="Proposed standard to launching desktop apps with Terminal=true"
arch=(any)
url="https://gitlab.freedesktop.org/Vladimir-csp/$pkgname"
makedepends=('scdoc')
checkdepends=('bats')
license=('GPL-3.0-or-later')
source=("${pkgname}-${pkgver}::$url/-/archive/v${pkgver}/${pkgname}-v${pkgver}.tar.gz")
sha256sums=('36e83306e012a17d98490ab8de468b3dcbab34f619cd85937ff2babc684f9bc0')
b2sums=('86c67ab8e7c63400d32d4526f907be22ab981d1ecfdfcdac3f15116ec4ef1b21da811a00205f4ee0941bf239a20c7c96e5d7dc17c327be4e3a89c71c001f4254')

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
