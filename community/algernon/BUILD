pkgname=algernon
pkgver=1.9
pkgdesc='Web server with built-in support for QUIC, HTTP/2, Lua, Markdown and Pongo2'
license=(MIT)

prepare() {
  export GOPATH="$srcdir"
  go get -d github.com/xyproto/algernon
  cd "$srcdir"/src/github.com/xyproto/algernon && git checkout "$pkgver"
}

build() {
  cd "$srcdir"/src/github.com/xyproto/algernon && go build
}

package() {
  install -D "$srcdir"/src/github.com/xyproto/algernon -t "$pkgdir"/bin/
}
