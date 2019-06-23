# Maintainer: Ondrej Svoboda <theodik@gmail.com>

pkgname=haas-proxy
pkgver=1.9
pkgrel=1
pkgdesc="Honeypot proxy is tool for redirectiong SSH session from local computer
to server of HaaS with additional information."
arch=('any')
url="https://haas.nic.cz/"
license=('GPL3')
install=$pkgname.install
source=("https://gitlab.labs.nic.cz/haas/proxy/raw/master/release/haas-proxy-1.9.tar.gz")
md5sums=('087775374888bb932e87dafb220bcf16')
depends=('python-twisted' 'python-cryptography' 'python-bcrypt' 'python-pyasn1' 'python-cachetools' 'python-requests' 'sshpass')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	python setup.py install --root="$pkgdir/" --optimize=1
	install -D -o root -g root -m 644 $startdir/haas-proxy.service $pkgdir/usr/lib/systemd/system/haas-proxy.service
	mkdir -p $pkgdir/etc
	echo "DEVICE_TOKEN=" > $pkgdir/etc/haas-proxy.conf
}
