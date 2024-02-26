pkgname=straw
pkgrel=1
pkgdesc="CLI tool to easily go-to projects all over your desktop and open a new tmux session in it"
arch=(x86_64)
url="https://github.com/siddhantmadhur/straw"
license=(MIT)
makedepends=(git go)
provides=(straw)
conflicts=(straw)
source=("straw::git+https://github.com/siddhantmadhur/straw.git")
sha256sums=(SKIP)

pkgver () {
    cd straw
    git describe --tags --abbrev=0
}


build() {
    cd straw
    go build -ldflags="-X 'main.version=${pkgver}'" -o straw 
}

package() {
    cd straw
    install -Dm755 straw -t "${pkgdir}/usr/bin" 
}
