_gemname=zabbixapi
pkgname=ruby-$_gemname
pkgver=3.0.0
pkgrel=1
pkgdesc="zabbix api ${pkgver}"
arch=(any)
url="https://github.com/express42/zabbixapi"
license=('MIT')
depends=(ruby)
options=(!emptydirs)
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
sha256sums=('e975a70655ac715d9a904bf6b8d7204e26e24f66e222bb8a998629cd467511c6')
noextract=($_gemname-$pkgver.gem)

package() {
  export PATH=/usr/bin:/bin
  local _gemdir="$(ruby -e'puts Gem.default_dir')"
  gem install --ignore-dependencies --no-user-install -i "$pkgdir/$_gemdir" -n "$pkgdir/usr/bin" $_gemname-$pkgver.gem
  rm "$pkgdir/$_gemdir/cache/$_gemname-$pkgver.gem"
}
