pkgname=neovim
pkgver=0.4.3
pkgrel=1
arch=('x86_64')
pkgdesc='Vim-fork focused on extensibility and usability'
url='https://neovim.io/'
license=('APACHE')
makedepends=('cmake' 'unzip' 'ninja')
source=("git+https://github.com/neovim/neovim.git#tag=v${pkgver}")
sha1sums=('SKIP')

build() {
  cd "${srcdir}/${pkgname}"
  make CMAKE_BUILD_TYPE=Release
}

check() {
  cd "${srcdir}/${pkgname}"
  ./build/bin/nvim --version
  ./build/bin/nvim --headless -u NONE -i NONE -c ':quit'
}

package() {
  cd "${srcdir}/${pkgname}"
  make CMAKE_INSTALL_PREFIX="${pkgdir}" install
}
