pkgname=python-packaging
pkgver=25.0
pkgrel=1
pkgdesc="Core utilities for Python packages"
arch=('x86_64')
url="https://pypi.org/project/packaging/"
license=('Apache')
depends=('python')
makedepends=('python-installer' 'python-flit-core')
source=(https://github.com/pypa/packaging/archive/${pkgver}/${pkgname#*-}-${pkgver}.tar.gz)
sha256sums=(d443872c98d677bf60f6a1f2f8c1cb748e8fe762d2bf9d3148b5599295b0fc4f)

build() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m flit_core.wheel
}

package() {
    cd ${pkgname#*-}-${pkgver}

    python3 -m installer -d ${pkgdir} dist/*.whl
}