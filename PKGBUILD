_proj=rarfile
#_python=python2 _pyver=2
#_python=python3 _pyver=""
pkgname="$_python-$_proj"
pkgver=2.6
pkgrel=3
pkgdesc="Rar archive reader for Python"
arch=(any)
url="https://pypi.python.org/pypi/$_proj"
license=(custom:ISC)
makedepends=("python$_pyver" python-docutils "python$_pyver-sphinx")
depends=("python$_pyver")
optdepends=("unrar: For decompression")
provides=("python-$_proj")
source=(
  "https://pypi.python.org/packages/source/r/$_proj/$_proj-$pkgver.tar.gz"
)
md5sums=(50ce3f3fdb9196a00059a5ea7b3739fd)

build() {
  cd "$srcdir/$_proj-$pkgver"
  "$_python" setup.py build
  make html SPHINXBUILD="sphinx-build$_pyver" BUILDDIR="_build-$pkgname"
}

package() {
  cd "$srcdir/$_proj-$pkgver"
  "$_python" setup.py install --root="$pkgdir" --optimize=1
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -D -m644 README.html "$pkgdir/usr/share/doc/$pkgname/README.html"
  cp -a "doc/_build-$pkgname/html" "$pkgdir/usr/share/doc/$pkgname/"
}
