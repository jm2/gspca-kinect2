# Maintainer: John-Michael Mulesa <jmulesa at gmail dot com>
# Contributor: William Gathoye <william + aur at gathoye dot be>
# Contributor: Hyacinthe Cartiaux <hyacinthe.cartiaux@free.fr>
# Contributor: Giorgio Gilestro <giorgio at gilest dot ro>
# Contributor: Richard Mathot <rim at odoo dot com>
_pkgbase=gspca-kinect2
pkgname=${_pkgbase}-dkms
pkgver=1.0
pkgrel=1
pkgdesc="A kernel module for using the Kinect 2 (XBox One) as a video/webcam."
url="https://github.com/jm2/gspca-kinect2"
license=("GPL")
arch=('i686' 'x86_64')
depends=('glibc' 'dkms')
conflicts=("${_pkgbase}")
optdepends=('linux-headers: Build the module for Arch kernel'
            'linux-lts-headers: Build the module for LTS Arch kernel')
source=(
    "git+https://github.com/jm2/gspca-kinect2"
)
sha512sums=('SKIP')

package() {
    install -Dm644 dkms.conf "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"

    sed -e "s/@PKGNAME@/${_pkgbase}/g" \
        -e "s/@PKGVER@/${_pkgbase}/g" \
        -i "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/dkms.conf"

    cp -dr --no-preserve='ownership' "${srcdir}/${_pkgbase}" "${pkgdir}/usr/src/${_pkgbase}-${pkgver}/src"
}
