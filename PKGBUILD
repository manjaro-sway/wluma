# Maintainer: torculus <20175597+torculus@users.noreply.github.com>
# Contributor: Maxim Baz <archlinux at maximbaz dot com>

pkgname=wluma
pkgver=4.6.1
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
b2sums=('50f414fba86912221757fccaec9614710114188f44f28d8a2392c375709bbb054af769cd9e9ab35f06dc51c8276ac8f255c48e39ae991e172dc19cbb5aa8bdb4'
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
