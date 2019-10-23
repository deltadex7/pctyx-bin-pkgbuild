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

_pkgfile="pctyxeditor_${pkgver}_linux64"
_pkgexec="PCtyxEditor"

options=(!strip)
makedepends=('unzip')

sha256sums=(
    '24264d6c5eaad9b391e996b7c21ee0f506e14fc4d1e24772864c2e9ac3b10ac8' 
    '1806a9867df6d242715593908e4f8ec24e2565586d466c7e401ac8eec6a071d9'
    'a24e3d5689d0cdbcf2487589a23ed3a7819237d858a1ea91201a3daef816fc69'
)

source=(
    "pctyx.desktop" 
    "https://github.com/XionUzuki/PCtyx/releases/download/v${pkgver}.${pkgrel}/${_pkgfile}.zip"
    "https://raw.githubusercontent.com/XionUzuki/PCtyx/master/LICENSE"
)

noextract=("$_pkgfile.zip")

prepare() {
    cd "$srcdir"
    mkdir -p $_pkgname
    bsdtar -x -f "$_pkgfile.zip" -C "$_pkgname" -s '|[^/]*/||'
    chmod +x "${_pkgname}/${_pkgexec}"
}

package() {
    cd "${srcdir}"
    install -dm755 "${pkgdir}/opt"
    cp -a --reflink=auto $_pkgname "${pkgdir}/opt/${_pkgname}"
    install -Dm664 -t "${pkgdir}/usr/share/licenses/${_pkgname}/" "LICENSE"
    install -Dm644 -t "${pkgdir}/usr/share/applications/" "${_pkgname}.desktop"
}

