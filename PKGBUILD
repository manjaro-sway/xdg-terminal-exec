# Maintainer: Max Gautier <mg@max.gautier.name>
pkgname=xdg-terminal-exec
pkgver=0.12.0
pkgrel=1
pkgdesc="Proposed standard to launching desktop apps with Terminal=true"
arch=(any)
url="https://gitlab.freedesktop.org/Vladimir-csp/$pkgname"
makedepends=('scdoc')
checkdepends=('bats')
license=('GPL-3.0-or-later')
source=("${pkgname}-${pkgver}::$url/-/archive/v${pkgver}/${pkgname}-v${pkgver}.tar.gz")
b2sums=('0b05070dd8e169d8b19a1f041cc8df69008a8f246c743e41092cc876bd8561b18cc1463cf5a75de3b61020536251a92567b872ba7b3457bf8a5fa2cc65306346')
sha256sums=('71abcfc50b1f408348097a29531b3621e50cc34de637bc73f14ef45f5021ae55')

check() {
    cd "$pkgname-v$pkgver"
    bats "test/"
}

build() {
    make -C "$pkgname-v$pkgver"
}

package() {
    cd "$pkgname-v$pkgver"
    install -Dm 755 -t "$pkgdir"/usr/bin "$pkgname"
    install -Dm 644 -t "$pkgdir"/usr/share/man/man1/ ${pkgname}.1.gz
}
