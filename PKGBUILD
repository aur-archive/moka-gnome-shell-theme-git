# Maintainer: Martin Wimpress <code@flexion.org>

_pkgname=moka-gnome-shell-theme
pkgname=${_pkgname}-git
pkgver=33.212e8bd
pkgrel=1
pkgdesc="Moka is the titular GNOME Shell theme of the Moka Project."
arch=('any')
url="https://github.com/moka-project/_${pkgname}"
license=('GPL3')
makedepends=('git')
conflicts=("${_pkgname}")
provides=("${_pkgname}")
replaces=("${_pkgname}")
options=(!strip)
source=(${_pkgname}::"git+https://github.com/moka-project/${_pkgname}.git")
sha256sums=('SKIP')

pkgver() {
    cd ${srcdir}/${_pkgname}
    echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

package() {
    install -d -m 755 "${pkgdir}"/usr/share/themes/Moka
    cp -dr --no-preserve=ownership "${_pkgname}"/Moka "${pkgdir}"/usr/share/themes/
    find "${pkgdir}"/usr/share/themes/ -type d -exec chmod 755 {} \;
    find "${pkgdir}"/usr/share/themes/ -type f -exec chmod 644 {} \;
}
