pkgname=groff
pkgver=1.23.0
pkgrel=2
pkgdesc="GNU troff text-formatting system"
arch=('x86_64')
url="https://www.gnu.org/software/groff/"
license=('GPL-3.0-or-later')
groups=('base-devel')
depends=(
    'gcc-libs'
    'perl'
)
options=('!emptydirs' '!makeflags')
source=(https://ftp.gnu.org/gnu/${pkgname}/${pkgname}-${pkgver}.tar.gz)
sha256sums=(6b9757f592b7518b4902eb6af7e54570bdccba37a871fddb2d30ae3863511c13)

build() {
    cd ${pkgname}-${pkgver}

    local configure_args=(
        ${configure_options}
    )

    PAGE=A4 ./configure "${configure_args[@]}"

    make
}

package() {
    cd ${pkgname}-${pkgver}

    make DESTDIR=${pkgdir} install
}
