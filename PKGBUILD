# Maintainer: Markus Opitz <mastero23 at gmail dot com>

pkgname=henplus
pkgver=0.9.8
pkgrel=2
pkgdesc="SQL shell written in Java"
arch=('i686' 'x86_64')
url="http://henplus.sourceforge.net/"
license=('GPL')
depends=('java-environment' 'bash')
makedepends=('apache-ant')
optdepends=('java-readline: readline support')
install=henplus.install
source=(http://sourceforge.net/projects/henplus/files/$pkgname-$pkgver.tar.gz
        henplus)
md5sums=('230d3bff07c54b4861c848582b077b35'
         '2d4a6b005a8371596aa552775eaa5b06')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ant jar
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  mkdir -p "$pkgdir/usr/share/java/henplus/"
  cp lib/commons-cli-1.2.jar lib/libreadline-java-0.8.0.jar \
    build/henplus.jar "$pkgdir/usr/share/java/henplus/"
  install -D doc/HenPlus.html "$pkgdir/usr/share/doc/henplus/HenPlus.html"
  install -D -m 755 "$srcdir/henplus" "$pkgdir/usr/bin/henplus"
}
