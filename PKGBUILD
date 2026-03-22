pkgname=python-packaging
pkgver=26.0
pkgrel=3
pkgdesc="Core utilities for Python packages"
arch=('x86_64')
url="https://pypi.org/project/packaging/"
license=('Apache')
depends=('python')
makedepends=(
    'python-build'
    'python-flit-core'
    'python-installer'
)
source=(https://github.com/pypa/packaging/archive/${pkgver}/${pkgname#*-}-${pkgver}.tar.gz)
sha256sums=(7b1995333d1d9a2d857ba85c493df323055e64248a45c2af32ebe9ae8dce663b)

build() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m build -wn --skip-dependency-check
}

package() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m installer -d ${pkgdir} dist/*.whl
}
