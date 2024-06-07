pkgname=neovim
pkgver=0.10.0
pkgrel=1
arch=('x86_64')
pkgdesc='Vim-fork focused on extensibility and usability'
url='https://neovim.io/'
license=('APACHE')
makedepends=('cmake' 'unzip' 'ninja' 'curl' 'gettext')
source=("https://github.com/neovim/neovim/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz")
sha1sums=('153eb935dd141eb29b8670792d616f109cb35752')

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
