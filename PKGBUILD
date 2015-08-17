# Maintainer: Jochen Schalanda <jochen+aur@schalanda.name>
_gemname=akami
pkgname=ruby-$_gemname
pkgver=1.2.2
pkgrel=1
pkgdesc='Ruby library for building web service security'
arch=(any)
url='https://github.com/savonrb/akami'
license=('MIT')
depends=('ruby' 'ruby-gyoku-0.4')
source=(https://rubygems.org/downloads/$_gemname-$pkgver.gem)
noextract=($_gemname-$pkgver.gem)

package() {
  cd "$srcdir"
  # _gemdir is defined inside package() because if ruby[gems] is not installed on
  # the system, makepkg will exit with an error when sourcing the PKGBUILD.
  local _gemdir="$(ruby -rubygems -e'puts Gem.default_dir')"

  gem install --no-user-install --ignore-dependencies -i "$pkgdir$_gemdir" \
    -n "$pkgdir/usr/bin" "$_gemname-$pkgver.gem"
}
sha256sums=('be43cd6e03e39216448f03e97be25a38bfdbd66b1ea28144acf5ace8e17e3888')
