# Maintainer: Arch Haskell Team <arch-haskell@haskell.org>
_hkgname=kit
pkgname=kit
pkgver=0.4.4
pkgrel=2
pkgdesc="A dependency manager for XCode (Objective-C) projects"
url="http://hackage.haskell.org/package/${_hkgname}"
license=('custom:BSD3')
arch=('i686' 'x86_64')
makedepends=('ghc' 'haskell-glob>=0.5' 'haskell-http=4000.0.9' 'haskell-missingh' 'haskell-quickcheck=2.1.1.1' 'haskell-bytestring=0.9.1.7' 'haskell-cmdargs>=0.3' 'haskell-containers=0.3.0.0' 'haskell-directory=1.0.1.1' 'haskell-filepath=1.1.0.4' 'haskell-json' 'haskell-mtl' 'haskell-network=2.2.1.7' 'haskell-process=1.0.1.3')
depends=('gmp')
options=('strip')
source=(http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz)
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup configure --prefix=/usr --docdir=/usr/share/doc/${pkgname} -O
    runhaskell Setup build
}
package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
    install -D -m644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
    rm -f ${pkgdir}/usr/share/doc/${pkgname}/LICENSE
}
md5sums=('a3d1a8e156a5a34b2a64209bb0702f6b')
