# Maintainer: David K david.dk949@gmail.com
_pkgname=ruc
pkgname="${_pkgname}-949sd"
pkgver=unknown
pkgrel=0
pkgdesc="Open the EDITOR. Write some code. Have it executed."
arch=('x86_64')
url="https://github.com/dk949/$_pkgname"
license=('MIT')
depends=()
makedepends=('rust')
provides=('ruc')
source=("$pkgname::git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    cd "$pkgname"
    awk '/version/ {print gensub(/^.*"([^"]*)".*$/, "\\1", "g")}' Cargo.toml
}

build() {
    cd "$pkgname"
    cargo build -r
}

package() {
    cd "$pkgname"

    cargo install --path . --root "$pkgdir/usr"
}
