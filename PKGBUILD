# Maintainer: torculus <20175597+torculus@users.noreply.github.com>
# Contributor: Maxim Baz <archlinux at maximbaz dot com>

pkgname=wluma
pkgver=4.5.1
pkgrel=1
license=('ISC')
pkgdesc='Automatic brightness adjustment based on screen contents and ALS'
url='https://github.com/maximbaz/wluma'
arch=('x86_64' 'aarch64')
depends=('dbus' 'vulkan-icd-loader' 'systemd-libs' 'glibc' 'gcc-libs' 'v4l-utils')
optdepends=('vulkan-driver: for using capturer=wlroots in config.toml'
            'wayland: for using capturer=wlroots in config.toml')
makedepends=('cargo' 'clang' 'systemd' 'marked-man')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/maximbaz/${pkgname}/archive/${pkgver}.tar.gz"
        "https://github.com/maximbaz/${pkgname}/releases/download/${pkgver}/${pkgname}-${pkgver}.tar.gz.asc")
b2sums=('569f697a8e12192428f5160177748a11ffab9efa003594567b28a6bdf08920d1578185bb02214f96e243ae527a7079901e7a700656cdc52d04058355942380a3'
        'SKIP')
validpgpkeys=('56C3E775E72B0C8B1C0C1BD0B5DB77409B11B601')

build() {
    cd "${pkgname}-${pkgver}"
    make build docs
}

check() {
    cd "${pkgname}-${pkgver}"
    make test
}

package() {
    cd "${pkgname}-${pkgver}"
    make install DESTDIR="${pkgdir}"
}
