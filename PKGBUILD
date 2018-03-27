# Maintainer: Ondrej Svoboda <theodik@gmail.com>

pkgname=haas-proxy
pkgver=1.6
pkgrel=1
pkgdesc="Honeypot proxy is tool for redirectiong SSH session from local computer
to server of HaaS with additional information."
arch=('any')
url="https://haas.nic.cz/"
license=('GPL3')
install=$pkgname.install
source=("https://gitlab.labs.nic.cz/haas/proxy/raw/master/release/haas-proxy-1.6.tar.gz")
md5sums=('c4b59ab0ccde5d1b1516df3148f3e193')
depends=('python-twisted' 'python-cryptography' 'python-pyasn1' 'python-cachetools' 'python-requests' 'sshpass')

package() {
	cd "$srcdir/$pkgname-$pkgver"
	python setup.py install --root="$pkgdir/" --optimize=1
	install -D -o root -g root -m 644 $startdir/haas-proxy.service $pkgdir/usr/lib/systemd/system/haas-proxy.service
	mkdir -p $pkgdir/etc
	echo "DEVICE_TOKEN=" > $pkgdir/etc/haas-proxy.conf
}
