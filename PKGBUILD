_proj=rarfile
pkgbase="python-$_proj"
pkgname=(python{2,3}-"$_proj")
pkgver=2.6
pkgrel=1
pkgdesc="Rar archive reader for Python"
arch=(any)
url="https://pypi.python.org/pypi/$_proj"
license=(custom:ISC)
makedepends=(python{3,2})
optdepends=("unrar: For decompression")
provides=("python-$_proj")
source=(
  "https://pypi.python.org/packages/source/r/$_proj/$_proj-$pkgver.tar.gz"
)
md5sums=(50ce3f3fdb9196a00059a5ea7b3739fd)

package_python3-rarfile() {
  cd "$srcdir/$_proj-$pkgver"
  "${PYTHON-python3}" setup.py install --root="$pkgdir" --optimize=1
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

package_python2-rarfile() {
  PYTHON=python2 package_python3-rarfile "$@"
}
