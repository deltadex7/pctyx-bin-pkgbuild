# Maintainer: Muhammad Hidayat <hidayat.pcd@gmail.com>

pkgname=pctyx-bin
_pkgname=pctyx
pkgver=150
pkgrel=3
pkgdesc="Semi-Cytus Simulator Project"
arch=(i686 x86_64)
url="https://github.com/XionUzuki/PCtyx"
license=("MIT")
provides=('pctyx')
conflicts=('pctyx')

_arch=64
[ "$CARCH" = "i686" ] && _arch=32


_pkgfile="pctyxeditor_${pkgver}_linux${_arch}"
_pkgexec="PCtyxEditor"

options=(!strip)
makedepends=('unzip')
depends=(libcups nss libxss gtk3-classic alsa-lib)

sha256sums=(
    '24264d6c5eaad9b391e996b7c21ee0f506e14fc4d1e24772864c2e9ac3b10ac8' 
    'a24e3d5689d0cdbcf2487589a23ed3a7819237d858a1ea91201a3daef816fc69'
)

[ "$CARCH" = "i686" ] && sha256sums+=('394ca7c40effa0db1ff74def8f5b3848ad5c617474b130a305de49785c8a5d70')
[ "$CARCH" = "x86_64" ] && sha256sums+=('abfae2813d0894769cc01567501c3faa3a0062bf6e3ce6f74d45f289e5484340')

source=(
    "pctyx.desktop" 
    "https://raw.githubusercontent.com/XionUzuki/PCtyx/master/LICENSE"
    "https://github.com/XionUzuki/PCtyx/releases/download/v${pkgver}.${pkgrel}/${_pkgfile}.zip"
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
    install -Dm664 -t "${pkgdir}/usr/share/licenses/${pkgname}/" "LICENSE"
    install -Dm644 -t "${pkgdir}/usr/share/applications/" "${_pkgname}.desktop"
}

