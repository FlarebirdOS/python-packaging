pkgname=python-packaging
pkgver=25.0
pkgrel=2
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
sha256sums=(15b6ba95eb12d8f99dcf215ea37cbea16812ef28358e8ef3d9344acb827acac1)

build() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m build -wn --skip-dependency-check
}

package() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m installer -d ${pkgdir} dist/*.whl
}
