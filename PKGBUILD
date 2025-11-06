pkgname=jacartauc
pkgverbase=3.3
pkgverminor=3.3763
pkgver=${pkgverbase}.${pkgverminor}
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
  ccid
  opensc
)

source=("https://www.aladdin-rd.ru/upload/downloads/JaCarta_UC/jacarta-${pkgverbase}/lunix/distributions/jacartauc_${pkgver}_rpm_x64.zip")
md5sums=("87FBBC3D0AEC669A564FFE79EDE2EC59")
options=(!strip !debug)

install="jacartauc.install"

package() {

  bsdtar -xvf "$srcdir"/jcsecurbio_*_x64.rpm -C "$pkgdir"
  bsdtar -xvf "$srcdir"/jcpkcs11-2_*_x64.rpm -C "$pkgdir"
  bsdtar -xvf "$srcdir"/jacartauc_*_x64.rpm -C "$pkgdir"

  mv "$pkgdir/tmp" "$pkgdir/opt/jacartauc/scripts" # keep installation scripts
  mv "$pkgdir/usr/lib64" "$pkgdir/usr/lib"         # arch just symlinks /usr/lib64 to /usr/lib
  gunzip "$pkgdir/opt/jacartauc/bin/JaCartaUC.gz"  # unpack binary

  patch "$pkgdir/opt/jacartauc/bin/jacartauc.sh" <"../pcscd_launch.patch"

}
