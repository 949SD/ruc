# Maintainer: David K david.dk949@gmail.com
pkgname=ruc
pkgver=unknown
pkgrel=0
pkgdesc="Open the EDITOR. Write some code. Have it executed."
arch=('any')
url="https://github.com/dk949/$pkgname"
license=('MIT')
depends=('python>=3.9')
provides=("$pkgname")
source=("git+$url")
md5sums=() #autofill using updpkgsums
sha256sums=('SKIP')

pkgver() {
    git -C "$pkgname" describe | sed 's/-/_/g'
}

build() {
    cd "$pkgname"
    make
}

package() {
    cd "$pkgname"

    make DESTDIR="$pkgdir/" PREFIX="/usr" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
