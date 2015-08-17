# Maintainer: Doug Newgard <scimmia22 at outlook dot com>
# Contributor: furester <furester at gmail dot com>
# Contributor: Changaco <changaco Î±Ï„ changaco Î´Î¿Ï„ net>

pkgname=python2-e_dbus-svn
_pkgname=python-e_dbus
pkgver=76210
pkgrel=5
pkgdesc="Python2 bindings for E_DBus - Development version"
arch=('i686' 'x86_64')
url="http://www.enlightenment.org"
license=('LGPL2.1')
depends=('e_dbus-svn' 'python2-dbus')
makedepends=('subversion')
provides=('python2-e_dbus')
conflicts=('python2-e_dbus')
options=('!libtool')
source=("svn+http://svn.enlightenment.org/svn/e/trunk/BINDINGS/python/$_pkgname")
md5sums=('SKIP')

pkgver() {
  cd "$SRCDEST/$_pkgname"

  LC_ALL=C svn info | awk '/Last Changed Rev/ {print $4}'
}

build() {
  cd "$srcdir/$_pkgname"

  PYTHON=/usr/bin/python2 \
  ./autogen.sh --prefix=/usr

  make
}

package() {
  cd "$srcdir/$_pkgname"

  make DESTDIR="$pkgdir" install
}
