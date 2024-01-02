pkgname=neovim
pkgver=0.9.5
pkgrel=1
arch=('x86_64')
pkgdesc='Vim-fork focused on extensibility and usability'
url='https://neovim.io/'
license=('APACHE')
makedepends=('cmake' 'unzip' 'ninja' 'curl' 'gettext')
source=("https://github.com/neovim/neovim/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz")
sha1sums=('62f25a75edd67cb24e1ed122c8df840bcffa5ca1')

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
