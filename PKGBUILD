# Maintainer: Max Gautier <mg@max.gautier.name>
_pkgname=xdg-terminal-exec
pkgname=$_pkgname
pkgver=r131.b269e8e
pkgrel=4
pkgdesc="Proposed standard to launching desktop apps with Terminal=true"
arch=(any)
url="https://github.com/Vladimir-csp/$_pkgname#commit=a09da6999c269bc7145232ed299f14dbace34a4b"
makedepends=('git')
license=('GPL3')
source=("git+$url")
sha256sums=('SKIP')
provides=('xdg-terminal-exec' 'xdg-terminal-exec-git')
conflicts=('xdg-terminal-exec-git')

pkgver() {
	cd "$_pkgname"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
	cd "$_pkgname"
    install -Dm 755 -t "$pkgdir"/usr/bin "$_pkgname"
    install -Dm 644 -t "$pkgdir"/usr/share/doc/"$_pkgname"/ README.md
}
