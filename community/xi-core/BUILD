pkgname=xi-core
pkgver=
pkgdesc="A modern editor with a backend written in Rust."
url="https://github.com/google/xi-editor"
license=(Apache-2.0)

prepare() {
  git clone https://github.com/google/xi-editor.git "$srcdir"
  cd "$srcdir" && git checkout -b 176c4002d873393b408fafc17fcbed0fc46b5057
}

build() {
  cd "$srcdir"/rust && cargo build --release
}

package() {
  install -D "$srcdir"/rust/target/release/xi-core -t "$pkgdir"/bin/
}
