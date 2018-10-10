# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=py-pandas
_pkgname=pandas
pkgver=0.20.3
pkgrel=0
pkgdesc="Powerful data structures for data analysis, time series,and statistics"
url="http://pandas.pydata.org/"
arch="noarch"
license="BSD"
depends="python py-dateutil py-numpy py-tz"
makedepends="linux-headers py-numpy-dev py-setuptools python2-dev python3-dev"
install=""
subpackages="py3-${pkgname#py-}:_py3 py2-${pkgname#py-}:_py2"
source="https://files.pythonhosted.org/packages/source/${_pkgname:0:1}/$_pkgname/$_pkgname-$pkgver.tar.gz"
builddir="$srcdir/$_pkgname-$pkgver"

build() {
	cd "$builddir"
	python2 setup.py build
	python3 setup.py build
}

package() {
	mkdir -p "$pkgdir"
}

_py() {
	local python="$1"
	pkgdesc="$pkgdesc ${python#python}"
	depends="$depends $python"
	subpkgarch="all"
	install_if="$pkgname=$pkgver-r$pkgrel $python"

	cd "$builddir"
	$python setup.py install --prefix=/usr --root="$subpkgdir"
}

_py2() {
	replaces="$pkgname"
	depends="${depends//py-/py2-}"
	_py python2
}

_py3() {
	depends="${depends//py-/py3-}"
	_py python3
}

sha512sums="891c7e04d075f96fadf3775e903472e279eaeaa4509eb0da81a74261a3ed86ff309de0b5a2c100ee93dd968fed1df6d7e426ca78785b2b36785fe7679218fdc5  pandas-0.20.3.tar.gz"
