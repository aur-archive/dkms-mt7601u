# Maintainer: Yong-hyu Ban <maneulyori@gmail.com>
pkgname=dkms-mt7601u
pkgver=v3.0.0.4
pkgrel=1
pkgdesc="Driver for Ralink MT7601U chipset wireless adaptors"
arch=('i686' 'x86_64')
url="http://www.ralinktech.com"
license=('GPL')
depends=('dkms' 'linux-headers')
conflicts=()
install=${pkgname}.install
options=(!strip)
source=("https://googledrive.com/host/0B2UOD7uMaJ2MNm9oLVBfWTlPM2M/DPO_MT7601U_LinuxSTA_3.0.0.4_20130913.tar.xz"
        "dkms.conf")

md5sums=('75dc9954bb5256cfb97bad1e7f4d9393'
         '95caf4e6ba262c9683867e207fe846d7')

package() {

    # Change src dir name
    mv ${srcdir}/DPO_MT7601U_LinuxSTA_3.0.0.4_20130913 ${srcdir}/$pkgname-$pkgver

    installDir="$pkgdir/usr/src/$pkgname-$pkgver"

    install -dm755 "$installDir"
    install -m644 "$srcdir/dkms.conf" "$installDir"
    install -dm755 "$pkgdir/etc/modprobe.d"

    cd "${srcdir}/${pkgname}-${pkgver}/"

    for d in `find . -type d`
    do
install -dm755 "$installDir/$d"
    done

for f in `find . -type f -o -type l`
    do
install -m644 "${srcdir}/${pkgname}-${pkgver}/$f" "$installDir/$f"
    done
}
