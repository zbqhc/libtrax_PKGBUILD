_name=trax
pkgname="$_name-git"
pkgver=1.0.0.r194.e8f88aa
pkgrel=1
pkgdesc="Reference implementation of the Visual Tracking eXchange protocol."
arch=('i686' 'x86_64')
url="http://www.votchallenge.net/"
license=('LGPL3')
groups=()
depends=()
makedepends=('git' 'cmake') # 'bzr', 'git', 'mercurial' or 'subversion'
provides=("trax")
conflicts=("trax")
replaces=()
backup=()
options=()
install=
source=('git+https://github.com/votchallenge/trax.git')
noextract=()
md5sums=('SKIP')

# Please refer to the 'USING VCS SOURCES' section of the PKGBUILD man page for
# a description of each element in the source array.

pkgver() {
    cd "$srcdir/$_name"
# Git, tags available
	printf "%s" "$(git describe --tags | sed 's/\([^-]*-\)g/r\1/;s/-/./g')"
	

}

prepare() {
	cd "$srcdir/$_name"
	mkdir -p build
}

build() {
	cd "$srcdir/$_name/build"
	cmake ..
	make
}


package() {
	cd "$srcdir/$_name/build"
	make DESTDIR="$pkgdir/" install
}
