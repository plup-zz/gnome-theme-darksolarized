# Maintainer: Your Name <youremail@domain.com>
pkgname=gnome-theme-darksolarized-git
pkgver=20120206
pkgrel=1
pkgdesc="DarkSolarized Theme"
arch=('any')
license=('GPL')
depends=('gtk-engine-murrine' )
makedepends=('git')
source=()
md5sums=() #generate with 'makepkg -g'

_gitroot=git://github.com/NPerry/gnome-theme-darksolarized.git
_gitname=gnome-theme-darksolarized
_destdir=$pkgdir/usr/share/themes/DarkSolarized

build() {
  cd "$srcdir"
  msg "Connecting to GIT server...."

  if [[ -d "$_gitname" ]]; then
    cd "$_gitname" && git pull origin
    msg "The local files are updated."
  else
    git clone "$_gitroot" "$_gitname"
  fi

  msg "GIT checkout done or server timeout"
}

package() {
  cd "$srcdir/$_gitname"

  mkdir -p $_destdir

  #Make sure anyone can write
  find . -type d -exec chmod 755 '{}' \;

  msg "Installing files..."
  cp -r *  $_destdir
}
