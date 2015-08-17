# Maintainer: Josh Klar <j@iv597.com>
# Contributor: Sven-Hendrik Haase <sh@lutzhaase.com>
# Contributor: grimi <grimi at poczta dot fm>

pkgname=urbanterror42
pkgver=4.2.006
pkgrel=1
pkgdesc="A team-based tactical shooter based on the Quake 3 Engine"
arch=('i686' 'x86_64')
url="http://www.urbanterror.net"
license=('GPL2')
depends=('sdl' 'openal' 'curl' 'urbanterror42-data')
makedepends=('mesa')
provides=('urbanterror')
source=("http://cdn.urbanterror.info/urt/42/zips/UrbanTerror42_full_006.zip"
        "urbanterror.sh"
        "urbanterror-server.sh"
        "urbanterror.desktop"
        "urbanterror.png")
md5sums=('65779cfa564345e7603a7a1aa61b54ea'
         '7812ece92ab71986ef038b3291adc412'
         'fbd3059497cf68769c0cbf02545c6bec'
         '08a99f4d7ad63024bc886e118ddcbc0f'
         'f9a57d898df73f43c6a85c8d8cc455ba')

package() {
  install -d $pkgdir/opt/urbanterror

  cd $pkgdir/opt/urbanterror

  # Copy binaries.
  [[ $CARCH == "i686" ]] && install -m755 $srcdir/UrbanTerror42/Quake3-UrT.i386 urbanterror
  [[ $CARCH == "i686" ]] && install -m755 $srcdir/UrbanTerror42/Quake3-UrT-Ded.i386 urbanterror-ded
  [[ $CARCH == "x86_64" ]] && install -m755 $srcdir/UrbanTerror42/Quake3-UrT.x86_64 urbanterror
  [[ $CARCH == "x86_64" ]] && install -m755 $srcdir/UrbanTerror42/Quake3-UrT-Ded.x86_64 urbanterror-ded

  # Copy desktop launcher.
  install -Dm644 $srcdir/urbanterror.desktop $pkgdir/usr/share/applications/urbanterror.desktop
  install -Dm644 $srcdir/urbanterror.png $pkgdir/usr/share/pixmaps/urbanterror.png

  # Copy launch scripts.
  install -Dm755 $srcdir/urbanterror.sh $pkgdir/usr/bin/urbanterror
  install -Dm755 $srcdir/urbanterror-server.sh $pkgdir/usr/bin/urbanterror-server
}

# vim: sw=2:ts=2 et:
