# Maintainer: Leonard de Ruijter <leonard@aur.archlinux.org>
# Contributor: Alexander Bau <abau[aT]imn.htwk-leipzig.de>
pkgname=ocaml-ocamlsdl
pkgver=0.9.1
pkgrel=3
pkgdesc="OCaml interface to the Simple DirectMedia Layer library"
arch=('i686' 'x86_64')
url="http://ocamlsdl.sf.net/"
license=('LGPL')
depends=('sdl_ttf' 'sdl_mixer' 'sdl_image')
makedepends=('ocaml-findlib')
optdepends=('sdl_gfx: SDL Graphic Primitives')
options=('!strip' 'staticlibs')
conflicts=('ocamlsdl')
provides=('ocamlsdl')
source=(http://sourceforge.net/projects/ocamlsdl/files/OCamlSDL/ocamlsdl-$pkgver/ocamlsdl-$pkgver.tar.gz)
md5sums=('c3086423991fcdc1ba468afd52fc112b')

build() {
  cd $srcdir/ocamlsdl-$pkgver
  ./configure --prefix=/usr --disable-ldconf
  make all
}

package() {
  cd $srcdir/ocamlsdl-$pkgver
  mkdir -p ${pkgdir}$(ocamlfind printconf destdir)
  make OCAMLFIND_LDCONF=ignore \
  OCAMLFIND_DESTDIR=${pkgdir}$(ocamlfind printconf destdir) install
}
