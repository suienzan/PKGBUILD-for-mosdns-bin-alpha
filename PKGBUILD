# Maintainer: suienzan <suienzan at gmail dot com>
_pkgname=mosdns
pkgname=${_pkgname}-bin
pkgver=5.0.0_alpha.2
pkgrel=1
pkgdesc="一个 DNS 转发器"
arch=('x86_64')
url="https://github.com/IrineSistiana/mosdns/"
license=('GPL3')
optdepends=('v2ray-domain-list-community: geosite.dat'
            'v2ray-geoip: geoip.dat'
            'v2ray-rules-dat-git: geosite.dat & geoip.dat')
backup=('etc/mosdns/config.yaml')
provides=('mosdns')

source=(
  "$pkgname-$pkgver.zip::https://github.com/IrineSistiana/mosdns/releases/download/v${pkgver//_/-}/mosdns-linux-amd64.zip"
  "config.yaml"
  "service"
  "sysusers"
  "tmpfiles"
)

sha256sums=('71baec6b4313fa273cea3dfa51a8da0c7fd19d7af265f61fc3466bc07da76329'
            '90b19d51d3426d822127767667a181b613a2db821912990622f515cfaf36180a'
            '8bb851c5413e0e25e18e9d912a35b1500b54531ea961d4fc6cc8416173311c17'
            'e6bc5034452123491e3901e2741183d528a29b00f1c01d6bbbb204549fee7306'
            '73c47567934255c4030ab06798a602989c257c187cf0c00132fbc839c902b096')

package() {
  install -Dm755 mosdns "$pkgdir"/usr/bin/mosdns
  install -Dm644 sysusers "$pkgdir/usr/lib/sysusers.d/mosdns.conf"
  install -Dm644 tmpfiles "$pkgdir/usr/lib/tmpfiles.d/mosdns.conf"
  install -Dm644 service "$pkgdir"/usr/lib/systemd/system/mosdns.service
  install -Dm644 config.yaml "$pkgdir"/etc/mosdns/config.yaml
}
