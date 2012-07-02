# Maintainer: Luke Turner <contact[at]luketurner[dot]org>
pkgname=graphite
pkgver=0.9.10
pkgrel=2
pkgdesc="Graphite provides real-time graphing for monitoring purposes."
url="http://www.graphite.wikidot.com"
arch=('x86_64' 'i686')
license=('GPLv3')
depends=()
optdepends=('statsd-git: feed data to Graphite')
makedepends=('python2-virtualenv')
conflicts=()
replaces=()
backup=()
install='graphite.install'
source=("uwsgi-graphite.yaml" "carbon.conf" "storage-schemas.conf")
md5sums=('2e7a06b7ed606228d02531b348c0b1d9' 'd7fdde32aa572642439824b3716fb2b5' '5718857b020c83a11d2f515b30a43f44')

build() {
    install $srcdir/carbon.conf /opt/graphene/conf/carbon.conf
    install $srcdir/storage-schemas.conf /opt/graphene/conf/storage-schemas.conf
    install $srcdir/uwsgi-graphite.yaml /opt/graphene/conf/uwsgi-graphite.yaml
}
# vim:set ts=2 sw=2 et:
