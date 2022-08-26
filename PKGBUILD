# Maintainer: jcchikikomori <jccorsanes@protonmail.com>
pkgname=eclipse-ide-java
_pkgver=4.24
pkgver=2022.06
pkgrel=1
pkgdesc="Eclipse IDE for Java Developers"
arch=('amd64')
options=(!strip)
url="https://www.eclipse.org/downloads/"
license=('MIT')
depends=('default-jre' 'libswt-gtk-4-jni')
source=("http://ftp-stud.fht-esslingen.de/pub/Mirrors/eclipse/technology/epp/downloads/release/2022-06/R/eclipse-java-2022-06-R-linux-gtk-x86_64.tar.gz"
        "eclipse-ide-java.desktop")
sha256sums=('DE5F4DC8AC87D6BE77FEE0D2F3CC447318FD9247551818CDA80EFF9CB330B60D'
            '4DEB974D9742545C0B623482965A3AAF2E4D81CB01C0C3AE2EA9F706176ABA15')

package() {
    cd "$srcdir"
    mkdir -p "${pkgdir}/opt/${pkgname}"
    cp -R "${srcdir}/eclipse/"* "${pkgdir}/opt/${pkgname}"
    # if [[ $CARCH = 'i686' ]]; then
    #     echo "TEST" >> /tmp/test.txt
    # fi

    mkdir -p "${pkgdir}/usr/bin/"
    mkdir -p "${pkgdir}/usr/share/applications/"
    # mkdir -p "${pkgdir}/usr/share/licenses/${pkgname}/"
    install -Dm 644 $pkgdir/opt/$pkgname/icon.xpm $pkgdir/usr/share/pixmaps/$pkgname.xpm
    install -Dm644 "${startdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications/"
    # for i in $(ls $srcdir/eclipse/license/ ); do
    #   ln -sf "/opt/${pkgname}/license/$i" "${pkgdir}/usr/share/licenses/${pkgname}/$i"
    # done
    ln -s "/opt/${pkgname}/eclipse" "${pkgdir}/usr/bin/eclipse-ide-java"
}
