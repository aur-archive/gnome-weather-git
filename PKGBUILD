# Maintainer: Yosef Or Boczko <yoseforb@gmail.com>

_pkgname=gnome-weather
pkgname=$_pkgname-git
pkgver=3.11.5
pkgrel=1
pkgdesc="Access current weather conditions and forecasts"
arch=('i686' 'x86_64')
license=('GPL')
depends=('gjs' "gtk3>=3.11.4" 'glib2' "libgweather>=3.9.5")
makedepends=('intltool'  'gobject-introspection' 'git')
options=('!libtool')
url="http://www.gnome.org/"
groups=('gnome-extra')
conflicts=('gnome-weather')
replaces=('gnome-weather')
provides=('gnome-weather=3.11.5')
install=gnome-weather.install
source=(git://git.gnome.org/gnome-weather)
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  git describe --always | sed 's|-|.|g'
}

build() {
  cd "$srcdir/$_pkgname"
  ./autogen.sh --prefix=/usr
  make
}

package() {
  cd "$srcdir/$_pkgname"
	make DESTDIR="$pkgdir" install
}

