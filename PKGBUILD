pkgname=jacartauc
pkgver=3.1.1.3473
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

source=("https://www.aladdin-rd.ru/upload/downloads/JaCarta_UC/jacarta-3.1/lunix/distributions/jacartauc_3.1.1.3473_rpm_x64.zip")
sha256sums=("d845f773aeac42497a6964cc637c0ff045d138c184d5bd15468c49cf900b507e")
options=(!strip)

install="jacartauc.install"

package() {
  
  bsdtar -xvf "$srcdir/jcsecurbio_1.1.2.180_x64.rpm" -C "$pkgdir"
  bsdtar -xvf "$srcdir/jcpkcs11-2_2.9.0.866_x64.rpm" -C "$pkgdir"
  bsdtar -xvf "$srcdir/jacartauc_3.1.1.3473_x64.rpm" -C "$pkgdir"
  
  chmod 1777 "$pkgdir/tmp" # fix permissions
  mv "$pkgdir/usr/lib64" "$pkgdir/usr/lib" # arch just symlinks /usr/lib64 to /usr/lib
  gunzip "$pkgdir/opt/jacartauc/bin/JaCartaUC.gz" # unpack binary

}