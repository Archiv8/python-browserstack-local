#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/browserstack-local/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/browserstack-local/discussions>

_langname="python"
_relname="browserstack-local"

pkgname="${_langname}-${_relname}"
pkgver=1.2.3
pkgrel=1
pkgdesc="Python bindings for BrowserStack Local"
arch=(
  "any"
)
url="http://github.com/browserstack/browserstack-local-python"
license=(
  "MIT"
)
depends=(
  "python"
  "python-psutil"
)
makedepends=(
  "python-setuptools"
)
_tarname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_tarname}.tar.gz"
)
sha512sums=(
  "96c66e25e2e390cf2ccbd821bb004fca2a93583047ab8dd034591a74f21fa894359c14a7fea841cbb78c4b30345bc208a760b0887a73a85f0fec6e057ff10776"
)

build() {

  cd "${_tarname}"

  python setup.py build
}

package() {

  cd "{_tarname}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
