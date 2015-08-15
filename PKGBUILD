# Maintainer: grimi <grimi at poczta dot fm>

_pkgname=fs-uae-game-center
pkgname=fs-uae-game-center-devel
pkgver=2.3.9dev
pkgrel=1
pkgdesc="FS-UAE Game Center is a graphical user interface for launching FS-UAE game configs (development version)."
arch=("any")
url="http://fs-uae.net/download-devel"
license=("GPL2")
depends=("fs-uae-devel" "xdg-utils" "python2-pygame" "python2-numpy" "python2-opengl" "python2-imaging" "python2-setuptools" "hicolor-icon-theme")
install="${pkgname}.install"
source=("http://fs-uae.net/devel/${pkgver}/${_pkgname}-${pkgver}.tar.gz")
provides=("fs-uae-game-center")
conflicts=("fs-uae-game-center")
md5sums=('e1e5bf4476451efec5dca790bcd69699')



build() {
   cd ${_pkgname}-${pkgver}

   python2 setup.py build
   make
}



package() {
   cd ${_pkgname}-${pkgver}

   python2 setup.py install --skip-build --prefix=/usr \
      --install-scripts=/usr/share/${_pkgname} \
      --install-lib=/usr/share/${_pkgname} --root="${pkgdir}"
   make install DESTDIR="${pkgdir}"

   install -d "${pkgdir}"/usr/bin
   ln -s /usr/share/${_pkgname}/${_pkgname} "${pkgdir}"/usr/bin/${_pkgname}
}


# vim:set ts=3 sw=3 et:

