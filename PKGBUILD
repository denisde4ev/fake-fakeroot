# Maintainer: Denis Dechev <deni2020@abv.bg> # NOT IN AUR
pkgname=fake-fakeroot-git
pkgver=1.0_1.25.3
pkgrel=1
pkgdesc="fake the fakeroot"
arch=('any')
url="https://github.com/deni2020/${pkgname%-git}"
license=('GPL3')
depends=('sh')
makedepends=('git')
provides=('fakeroot')
conflicts=('fakeroot')
replaces=('fakeroot')
# source=("${pkgname%-git}::git+${url}.git")
source=("fake-fakeroot")
md5sums=('SKIP')

pkgver() {
	# cd "$srcdir/${pkgname%-git}"
	cd "$srcdir"

	ver=$(./fake-fakeroot --version 2>/dev/null | grep -o '[^ ]*$')
	# echo "1.0.0_${ver:?'coud not get fake-fakeroot version'}"
	# printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
	echo "1.0_${ver}"
}

check() {
	# cd "$srcdir/${pkgname%-git}" 
	cd "$srcdir"

	./fake-fakeroot sh -c '[ X"$FAKED_MODE" = Xunknown-is-root ] && [ -n "$FAKEROOTKEY" ] || exit 1'
}

package() {
	# cd "$srcdir/${pkgname%-git}" 
	cd "$srcdir"
	install -Dm755 -t "$pkgdir/usr/bin/" fake-fakeroot
}
