# Maintainer: Luke Turner <contact[at]luketurner[dot]org>
pkgname=graphite-full
pkgver=0.9.10
pkgrel=2
pkgdesc="Graphite provides real-time graphing for monitoring purposes."
url="http://www.graphite.wikidot.com"
arch=('x86_64' 'i686')
license=('GPLv3')
depends=('cairo')
optdepends=('statsd-git: feed data to Graphite')
makedepends=('python2-virtualenv')
conflicts=()
replaces=()
backup=()
install='graphite.install'
source=("uwsgi-graphite.yaml" "carbon.conf" "storage-schemas.conf" "local_settings.py")
md5sums=('2e7a06b7ed606228d02531b348c0b1d9' 'd7fdde32aa572642439824b3716fb2b5' '5718857b020c83a11d2f515b30a43f44' '4217ca7f5f4e76fc0de266d81d20b5b1')

build() {
    virtualenv2 --distribute --system-site-packages "$pkgdir/opt/graphite"
    "$pkgdir/opt/graphite/bin/pip-2.7" install whisper uwsgi Django tagging django-tagging simplejson http://cairographics.org/releases/py2cairo-1.8.10.tar.gz carbon graphite-web --install-option="--prefix=$pkgdir/opt/graphite" --install-option="--install-lib=$pkgdir/opt/graphite/webapp"
    install -D $srcdir/uwsgi-graphite.yaml $pkgdir/opt/graphite/conf/uwsgi-graphite.yaml
    install -D $srcdir/carbon.conf $pkgdir/opt/graphite/conf/carbon.conf
    install -D $srcdir/storage-schemas.conf $pkgdir/opt/graphite/conf/storage-schemas.conf
    install -D $srcdir/local_settings.py $pkgdir/opt/graphite/webapp/graphite/local_settings.py
}

# vim:set ts=2 sw=2 et:
