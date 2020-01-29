# Maintainer: BlackIkeEagle <ike DOT devolder AT gmail DOT com>
# Contributor: kevku <kevku@gmx.com>

pkgname=kodi-addon-inputstream-rtmp
pkgver=2.0.7
_codename=Leia
pkgrel=1
pkgdesc="RTMP input stream add-on for Kodi"
arch=('x86_64')
url="https://github.com/xbmc/inputstream.rtmp"
license=('GPL2')
groups=('kodi-addons' 'kodi-addons-inputstream')
depends=('kodi' 'rtmpdump' 'p8-platform')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/inputstream.rtmp/archive/$pkgver-$_codename.tar.gz")
sha512sums=('a67be952bae24083403e5a8783c86af51b24d9f2759fdeb1e4bdc42912c55381189c5925b52743ce79dd03a3e510c65d4972728e2355082b91d73857b1657cd9')

build() {
    cd "inputstream.rtmp-$pkgver-$_codename"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "inputstream.rtmp-$pkgver-$_codename"
	make DESTDIR="$pkgdir/" install
}
