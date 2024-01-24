# Maintainer: Kimiblock Moe
_name="Amulet-LevelDB"
pkgname=python-amulet-leveldb-git
pkgdesc="A Cython wrapper for Mojang's modified LevelDB library."
url="https://github.com/Amulet-Team/Amulet-LevelDB"
license=(unknown)
arch=(any)
pkgver=r29.11aa86c
pkgrel=2
makedepends=(python-setuptools git)
depends=(python python-versioneer python-portalocker python-leveldb)
source=(
	"git+https://github.com/Amulet-Team/Amulet-LevelDB.git"
)
md5sums=(
	"SKIP"
)
provides=(python-amulet-leveldb-git python-amulet-leveldb)

function pkgver() {
	cd "${srcdir}/${_name}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

function prepare() {
	cd "${srcdir}/${_name}"
	git submodule init
	git submodule update
}

function build() {
	cd "${srcdir}/${_name}"
	python setup.py build
}

function package() {
	cd "${srcdir}/${_name}"
	python setup.py install --root="$pkgdir" --optimize=1
}
