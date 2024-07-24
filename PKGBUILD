pkgname=neovim
pkgver=0.10.1
pkgrel=1
arch=('x86_64')
pkgdesc='Vim-fork focused on extensibility and usability'
url='https://neovim.io/'
license=('APACHE')
makedepends=('cmake' 'unzip' 'ninja' 'curl' 'gettext')
source=("https://github.com/neovim/neovim/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz")
sha1sums=('bd14711e16830e00e5e9036a4d7f757d1e42d3e7')

build() {
  cd "${pkgname}-${pkgver}"
  make CMAKE_BUILD_TYPE=Release \
      CMAKE_INSTALL_PREFIX=/usr
}

check() {
  cd "${pkgname}-${pkgver}"
  ./build/bin/nvim --version
  ./build/bin/nvim --headless -u NONE -i NONE -c ':quit'
}

package() {
  cd "${pkgname}-${pkgver}"
  make DESTDIR=${pkgdir} install
}
