
_name=gnuplot_kernel
pkgname=jupyter-${_name}
pkgver=0.3.0
pkgrel=0
pkgdesc="A Jupyter kernel for gnuplot"
arch=('any')
url="https://github.com/has2k1/gnuplot_kernel"
license=('BSD')
depends=('jupyter' 'jupyter-metakernel' 'jupyter-notebook' 'gnuplot')
makedepends=('python-pip')
optdepends=()
source=("${_name}-${pkgver}::git+https://github.com/has2k1/${_name}#tag=v${pkgver}")
sha256sums=('SKIP')

build() {
  cd "$srcdir"/$_name-${pkgver}
  python setup.py build
}

package() {
  cd "$srcdir"/$_name-${pkgver}
  python setup.py install --root="$pkgdir/" --optimize=1 --skip-build
  install -D -m644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
