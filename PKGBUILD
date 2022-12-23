# Maintainer: suienzan <suienzan at gmail dot com>
_pkgname=mosdns
pkgname=${_pkgname}-bin
pkgver=5.0.0_rc.0
pkgrel=1
pkgdesc="一个 DNS 转发器"
arch=('x86_64')
url="https://github.com/IrineSistiana/mosdns/"
license=('GPL3')
backup=('etc/mosdns/config.yaml')
provides=('mosdns')

source=(
  "$pkgname-$pkgver.zip::https://github.com/IrineSistiana/mosdns/releases/download/v${pkgver//_/-}/mosdns-linux-amd64.zip"
  "service"
  "sysusers"
  "tmpfiles"
)

sha256sums=('ed701f120854b79da64d6660384db0c888946c990e50c50fbd8fea7bc2fce2f7'
            '8bb851c5413e0e25e18e9d912a35b1500b54531ea961d4fc6cc8416173311c17'
            'e6bc5034452123491e3901e2741183d528a29b00f1c01d6bbbb204549fee7306'
            '73c47567934255c4030ab06798a602989c257c187cf0c00132fbc839c902b096')

package() {
  install -Dm755 mosdns "$pkgdir"/usr/bin/mosdns
  install -Dm644 sysusers "$pkgdir"/usr/lib/sysusers.d/mosdns.conf
  install -Dm644 tmpfiles "$pkgdir"/usr/lib/tmpfiles.d/mosdns.conf
  install -Dm644 service "$pkgdir"/usr/lib/systemd/system/mosdns.service
}
