# Maintainer: Baptiste Jonglez <baptiste--aur at jonglez dot org>
pkgname=lib32-pdcurses
pkgver=3.4
pkgrel=1
pkgdesc="Cross-platform (DOS, OS/2, Win32, X11 and SDL) curses implementation, built against SDL"
arch=('x86_64')
url="http://pdcurses.sourceforge.net/"
license=('GPL')
depends=('bash' 'lib32-sdl')
options=()
source=(http://downloads.sourceforge.net/pdcurses/PDCurses-$pkgver.tar.gz)
md5sums=('4e04e4412d1b1392a7f9a489b95b331a')

build() {
  cd "$srcdir/PDCurses-$pkgver"

  make -C sdl1 libs CFLAGS="-O2 -m32"
}

package() {
  cd "$srcdir/PDCurses-$pkgver"
  mkdir -p $pkgdir/usr/lib32
  install -c -m 644 sdl1/libpdcurses.a $pkgdir/usr/lib32/libpdcurses.a
}
