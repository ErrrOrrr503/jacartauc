pkgname=jacartauc
pkgver=3.1.0.3465
pkgrel=1
pkgdesc="JaCarta Unified Client"
arch=("x86_64")
url="https://www.aladdin-rd.ru/support/downloads/jacarta/"

depends=(
  at-spi2-core
  bash
  cairo
  dbus
  fontconfig
  freetype2
  gcc-libs
  gdk-pixbuf2
  glib2
  glibc
  gtk3
  libdrm
  libx11
  libxcb
  libxext
  libxkbcommon
  libxkbcommon-x11
  libxrender
  pango
  pcsclite
  systemd-libs
  zlib
)

source=("https://www.aladdin-rd.ru/upload/downloads/JaCarta_UC/jacarta-3.1/lunix/distributions/jacartauc_3.1.0.3465_rpm_x64.zip")
sha256sums=("3dc97171286794bbf1fa1a925dcfa7597555c446e5ab41f7f56454e1ecb20a2a")
options=(!strip)

install="jacartauc.install"

package() {
  
  bsdtar -xvf "$srcdir/jcsecurbio_1.1.2.180_x64.rpm" -C "$pkgdir"
  bsdtar -xvf "$srcdir/jcpkcs11-2_2.9.0.863_x64.rpm" -C "$pkgdir"
  bsdtar -xvf "$srcdir/jacartauc_3.1.0.3465_x64.rpm" -C "$pkgdir"
  
  chmod 1777 "$pkgdir/tmp" # fix permissions
  mv "$pkgdir/usr/lib64" "$pkgdir/usr/lib" # arch just symlinks /usr/lib64 to /usr/lib
  gunzip "$pkgdir/opt/jacartauc/bin/JaCartaUC.gz" # unpack binary

}