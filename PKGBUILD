# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: eolianoe <eolianoe At GoogleMAIL DoT com>
# Contributor: Andrey Mikhaylenko <neithere at gmail dot com>

_py="python"
_pyver="$( \
  "${_py}" \
    -V | \
    awk \
      '{print $2}')"
_pymajver="${_pyver%.*}"
_pyminver="${_pymajver#*.}"
_pynextver="${_pymajver%.*}.$(( \
  ${_pyminver} + 1))"
_pkg=pkginfo
pkgname="${_py}-${_pkg}"
pkgver=1.2.1
pkgrel=1
_pkgdesc=(
  'Query metadatdata from sdists'
  '/ bdists / installed packages'
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'any'
)
url="https://pypi.python.org/pypi/${_pkg}"
_url="http://pythonhosted.org/${_pkg}"
license=(
  'Python'
)
depends=(
  "${_py}>=${_pymajver}"
  "${_py}<${_pynextver}"
)
makedepends=(
  "${_py}-setuptools"
)
# _pypi="http://pypi.python.org/packages/source"
_pypi="https://pypi.io/packages/source"
source=(
  "${_pypi}/${_pkg:0:1}/${_pkg}/${_pkg}-${pkgver}.tar.gz"
)
sha256sums=(
  'ad3f6dfe8a831f96a7b56a588ca874137ca102cc6b79fc9b0a1c3b7ab7320f3c'
)

package() {
  cd \
    "${srcdir}/${_pkg}-${pkgver}"
  ${_py} \
    setup.py \
    install \
    --root="${pkgdir}" \
    --optimize=1
}
