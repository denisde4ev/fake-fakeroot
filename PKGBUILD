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
source=("${pkgname%-git}::git+${url}.git")
# source=("fake-fakeroot")
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}" || cd "$srcdir"

	ver=$(./fake-fakeroot --version 2>/dev/null | grep -o '77[^ ]*$')
	# echo "1.0.0_${ver:?'coud not get fake-fakeroot version'}"
	echo "1.0_${ver}"
}
#######################################################







# The examples below are not absolute and need to be adapted to each repo. The
# primary goal is to generate version numbers that will increase according to
# pacman's version comparisons with later commits to the repo. The format
# VERSION='VER_NUM.rREV_NUM.HASH', or a relevant subset in case VER_NUM or HASH
# are not available, is recommended.

## Bazaar
#	printf "r%s" "$(bzr revno)"
#
## Git, tags available
#	printf "%s" "$(git describe --long | sed 's/\([^-]*-\)g/r\1/;s/-/./g')"
#
## Git, no tags available
#	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
#
## Mercurial
#	printf "r%s.%s" "$(hg identify -n)" "$(hg identify -i)"
#
## Subversion
#	printf "r%s" "$(svnversion | tr -d 'A-z')"
#}
#
#prepare() {
#	cd "$srcdir/${pkgname%-git}"
#	patch -p1 -i "$srcdir/${pkgname%-git}.patch"
#}

# build() {
	# cd "$srcdir/${pkgname%-git}"
	# ./autogen.sh
	# ./configure --prefix=/usr
	# make
	# echo BUILD.........
# }

check() {
	cd "$srcdir/${pkgname%-git}" || cd "$srcdir"

	./fake-fakeroot sh -c '[ X"$FAKED_MODE" = Xunknown-is-root ] && [ -n "$FAKEROOTKEY" ] || exit 1'
}

package() {
	cd "$srcdir/${pkgname%-git}" || cd "$srcdir"
	install -Dm755 -t "$pkgdir/usr/bin/" fake-fakeroot
}
