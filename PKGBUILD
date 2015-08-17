#Maintainer: Alexey Stukalov <astukalov@gmail.com>
pkgname=smartgit-ea
pkgver=4_rc_1
pkgrel=1
pkgdesc="A Git GUI client written in Java. Early Access Series"
arch=("any")
url="http://www.syntevo.com/smartgit/early-access.html"
license=('custom')
depends=("java-runtime" "desktop-file-utils" "sh" "git" "gtk2")
optdepends=("mercurial: hg repositiories support")
provides=(smartgit=$pkgver)
# package version as it appears in the name of tar.gz archive file
_pkgver=${pkgver//_/-}
_pkgname=${pkgname//-ea*/}
# folder within tar.gz archive
_pkgfolder="$_pkgname-$_pkgver"
source=(http://www.syntevo.com/download/${_pkgname}/${_pkgname}-generic-${_pkgver}.tar.gz
        smartgit-ea.desktop)
install="smartgit-ea.install"
md5sums=('f97767a8cb320d2b322e79b682c8841d'
         'd3e20fd9001c3f33fc812d7e3b43fd8f')

package() {
    cd "$srcdir"

    #install -D -m644 "${_pkgfolder}"/licenses/* "${pkgdir}/usr/share/licenses/${pkgname}"
    mkdir -p "${pkgdir}"/opt
    mv "${_pkgfolder}" ${pkgdir}/opt/${pkgname} || return 1

    install -D -m644 smartgit-ea.desktop "${pkgdir}"/usr/share/applications/${pkgname}.desktop
}

