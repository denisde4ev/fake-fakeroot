# Maintainer: Denis Dechev <deni2020@abv.bg> # NOT IN AUR
pkgname=fake-fakeroot-git
pkgver=r0.0
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
source=("fake-fakeroot")
md5sums=('SKIP')

pkgver() {
	cd "$startdir"

	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	sed --in-place -e "s/^version=UNKNOWN$/version=$(pkgver)/" "$srcdir/fake-fakeroot" || true
}

check() {
	"$srcdir/fake-fakeroot" -- sh -c '[ X"$FAKED_MODE" = Xunknown-is-root ] && [ -n "$FAKEROOTKEY" ] || exit 1'
}

package() {
	install -Dm755 "$srcdir/fake-fakeroot" "$pkgdir/usr/bin/fakeroot"
}
