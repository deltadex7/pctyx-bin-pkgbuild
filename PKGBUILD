# Maintainer: Muhammad Hidayat <hidayat.pcd@gmail.com>

pkgname=pctyx-bin
_pkgname=pctyx
pkgver=150
pkgrel=2
pkgdesc="Semi-Cytus Simulator Project"
arch=("x86_64")
url="https://github.com/XionUzuki/PCtyx"
license=("MIT")
provides=('pctyx')
conflicts=('pctyx')

makedepends=('unzip')

sha256sums=(
    '24264d6c5eaad9b391e996b7c21ee0f506e14fc4d1e24772864c2e9ac3b10ac8' 
    '1806a9867df6d242715593908e4f8ec24e2565586d466c7e401ac8eec6a071d9'
    'a24e3d5689d0cdbcf2487589a23ed3a7819237d858a1ea91201a3daef816fc69'
)

source=(
    "pctyx.desktop" 
    "https://github.com/XionUzuki/PCtyx/releases/download/v${pkgver}.${pkgrel}/pctyxeditor_${pkgver}_linux64.zip"
    "https://raw.githubusercontent.com/XionUzuki/PCtyx/master/LICENSE"
)

prepare() {
    mv "${srcdir}/pctyxeditor_${pkgver}_linux64" "${srcdir}/${_pkgname}"
    cd "${srcdir}/${_pkgname}"
}

package() {
    install -dm755 "${pkgdir}/opt/${_pkgname}"
    install -dm755 "${pkgdir}/usr/share/licenses/${_pkgname}"

}
