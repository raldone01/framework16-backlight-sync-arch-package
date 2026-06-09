# Maintainer: raldone01 <raldone01@gmail.com>
pkgname=framework16-backlight-sync-git
pkgver=r3.ff40612
pkgrel=1
pkgdesc="Framework 16 keyboard/numpad backlight sync daemon"
arch=('any')
url="https://github.com/MiguelAgueda/framework16-backlight-sync"
license=('MIT')
depends=('python')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=("${pkgname%-git}::git+https://github.com/MiguelAgueda/framework16-backlight-sync.git")
sha256sums=('SKIP')

pkgver() {
  cd "${pkgname%-git}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

package() {
  cd "${pkgname%-git}"

  install -Dm755 fw16_backlight_sync.py "$pkgdir/usr/bin/fw16-backlight-sync"

  install -Dm644 systemd/fw16-backlight-sync.service "$pkgdir/usr/lib/systemd/system/fw16-backlight-sync.service"
  sed -i 's|/usr/local/bin|/usr/bin|g' "$pkgdir/usr/lib/systemd/system/fw16-backlight-sync.service"

  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/${pkgname}/LICENSE"
}
