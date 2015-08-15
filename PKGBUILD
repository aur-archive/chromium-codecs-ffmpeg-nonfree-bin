# $Id:$
# Contributor: Balwinder S "bsd" Dheeman (bdheeman AT gmail.com)
# Maintainer: Balwinder S "bsd" Dheeman (bdheeman AT gmail.com)

pkgname=chromium-codecs-ffmpeg-nonfree-bin
_pkgname=chromium-codecs-ffmpeg-extra
_pkgver=svn20120105r116462
_pkgpre=18.0.997.0~
_pkgsuf=0ubuntu1~ucd1~natty
pkgver=18.0.997.0.116462
pkgrel=1
pkgdesc="Extra ffmpeg codecs for 'chromium-browser-bin' (View/Watch HTML5 videos)"
arch=('i686' 'x86_64')
url=https://launchpad.net/chromium-browser/
license=('GPL' 'LGPL' 'custom')
depends=('chromium-browser-bin' 'libvpx')
replaces=('chromium-codecs-ffmpeg-extra-ppa')
options=('!strip')
install=${pkgname}.install

_tgtdir=opt
_gogdir=chromium-browser
case "$CARCH" in
    i686|i[3-5]86)
	_bldarch='i386'
	md5sums=('9eeac3e663311d1d07d57bf788e1158d');;
    x86_64|amd64)
	_bldarch='amd64'
	md5sums=('b0fcb0fe919da78cb3a5fdf85363c2c9');;
    # The following should not happen; provided you're using 'makepkg' ;)
    *) error "Unknown or invalid CARCH=$CARCH"; exit 1
esac

_pkgname=chromium-codecs-ffmpeg-extra
_url=http://ppa.launchpad.net/chromium-daily/ppa/ubuntu/pool/main/c/chromium-browser
source=(${_url}/${_pkgname}_${_pkgpre}${_pkgver}-${_pkgsuf}_${_bldarch}.deb)

build() {
    msg2 "Extracting files..."
    cd "$srcdir"
    ar x ${_pkgname}_${_pkgpre}${_pkgver}-${_pkgsuf}_${_bldarch}.deb
    tar xf data.tar.lzma
    mkdir -p $pkgdir/${_tgtdir}/${_gogdir}
    cp -d $srcdir/usr/lib/${_gogdir}/lib* $pkgdir/${_tgtdir}/${_gogdir}
    mv $pkgdir/${_tgtdir}/${_gogdir}/libffmpegsumo.so $pkgdir/${_tgtdir}/${_gogdir}/libffmpegsumo.so.NONFREE

#    msg2 "Making it nice..."
#    install -Dm644 $srcdir/usr/share/doc/${_pkgname}/copyright \
#	$pkgdir/usr/share/licenses/${pkgname}/LICENSE.txt
#    cat >>$pkgdir/usr/share/licenses/${pkgname}/LICENSE.txt <<-EOT
#On ArchLinux machines, a complete text of the GNU General Public
#License can be found in '/usr/share/licenses/common/GPL' and a text of the
#GNU Lesser General Public License is in '/usr/share/licenses/common/LGPL' ;)
#EOT
}

# vim:set ts=4 sw=4 et:
