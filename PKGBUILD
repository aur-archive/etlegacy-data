# Maintainer: Babets
pkgname=etlegacy-data
pkgver=2.70rc1
pkgrel=2

pkgdesc="ET: Legacy is a project that aims to create a fully compatible client/server for the popular online FPS game Wolfenstein: Enemy Territory. Data files."
arch=('any')
url="http://etlegacy.com/"
license=('custom: enemy territory')
source=("http://ftp.gwdg.de/pub/misc/ftp.idsoftware.com/idstuff/et/linux/et-linux-2.60.x86.run")
md5sums=('2d2373f29f02e18d365d7f1860eee435')

build() {
  cd $srcdir
  chmod +x et-linux-2.60.x86.run
  ./et-linux-2.60.x86.run --noexec --target $srcdir
}

package() {
cd "$srcdir"

  # create destination directories
  install -d $pkgdir/usr/share/etlegacy/etmain
  install -d $pkgdir/usr/share/licenses/$pkgname

  # copy enemy-territory's pk3 files (even mp_bin.pk3 that cointains binaries!)
  install -Dm 644 etmain/{mp_bin,pak0,pak1,pak2}.pk3 $pkgdir/usr/share/etlegacy/etmain

  # install enemy territory license
  install -Dm 644 Docs/EULA_Wolfenstein_Enemy_Territory.txt $pkgdir/usr/share/licenses/$pkgname

}

# vim:set ts=2 sw=2 et:
