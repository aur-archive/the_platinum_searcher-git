# Maintainer: kusakata <shohei atmark kusakata period com>

pkgname=the_platinum_searcher-git
pkgver=1.6.5.0.54acefa
pkgrel=1
pkgdesc="A code search tool similar to ack and the_silver_searcher(ag)"
arch=('i686' 'x86_64')
url="https://github.com/monochromegane/the_platinum_searcher"
license=('MIT')
depends=('glibc')
makedepends=('git' 'go' 'mercurial')
provides=('the_platinum_searcher')
md5sums=('SKIP')
_gourl="github.com/monochromegane/the_platinum_searcher"

build() {
	GOPATH=$srcdir go get -v -d -x $_gourl
	cd $srcdir/src/github.com/monochromegane/the_platinum_searcher
	GOPATH=$srcdir go build -o ../../../../pt
}

package() {
	cd "$srcdir"
	install -Dm755 pt "$pkgdir/usr/bin/pt"
	cd "$srcdir/src/$_gourl"
	install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}