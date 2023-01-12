pkgname=maddy-config-grug
pkgver=0.0.1
pkgver() {
  # Use number of revisions and hash as version
  cd "$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}
pkgrel=1
arch=('any')
pkgdesc="Maddy config for grug"
url="https://git.grug.se/admin/maddy-config-grug"
license=('MIT')
makedepends=()
provides=()
conflicts=()
install="script.install"
package() {
  depends+=(maddy)
  depends+=(server-config-grug)

  mkdir -p "$pkgdir/etc/systemd/system/maddy.service.d"
  cp override.conf "$pkgdir/etc/systemd/system/maddy.service.d/"
  cp maddy-reload.path "$pkgdir/etc/systemd/system/"
  cp maddy-reload.service "$pkgdir/etc/systemd/system/"
  cp -r maddy-config-grug "$pkgdir/etc/maddy-config-grug"
}
