# Maintainer: Alan Young <harleypig@harleypig.com>

pkgname=packer-git
pkgver=238.809dc71
pkgrel=1
pkgdesc='Bash wrapper for pacman and aur'
url="https://github.com/harleypig/packer"
license=('GPL3')
arch=('any')
makedepends=('git')
depends=('grep' 'sed' 'bash' 'curl' 'pacman' 'jshon' 'sudo')
conflicts=('packer')
optdepends=('customizepkg: apply customizepkg modifications')
source=("${pkgname}::git+https://github.com/harleypig/packer.git#branch=master")
sha256sums=('SKIP')
provides=('packer')

pkgver() {
  #cd "${srcdir}/${pkgname}"
  echo "$(git rev-list --count HEAD).$(git rev-parse --short HEAD)"
}

package() {
  cd "${srcdir}/${pkgname}"
  mkdir -p ${pkgdir}/usr/bin
  mkdir -p ${pkgdir}/usr/share/man/man8
  install -D -m 755 packer "${pkgdir}/usr/bin/packer"
  install -D -m 644 packer.8 "${pkgdir}/usr/share/man/man8/packer.8"
}
