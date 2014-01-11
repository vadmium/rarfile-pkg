_proj=rarfile
#_python=python2 _pyver=2
#_python=python3 _pyver=""
pkgbase="python-$_proj"
pkgname="$_python-$_proj"
pkgver=2.6
pkgrel=2
pkgdesc="Rar archive reader for Python"
arch=(any)
url="https://pypi.python.org/pypi/$_proj"
license=(custom:ISC)
makedepends=("python$_pyver")
depends=("python$_pyver")
optdepends=("unrar: For decompression")
provides=("python-$_proj")
source=(
  "https://pypi.python.org/packages/source/r/$_proj/$_proj-$pkgver.tar.gz"
)
md5sums=(50ce3f3fdb9196a00059a5ea7b3739fd)

package() {
  cd "$srcdir/$_proj-$pkgver"
  "$_python" setup.py install --root="$pkgdir" --optimize=1
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
