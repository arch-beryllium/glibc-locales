pkgname=glibc-locales
pkgver=0.1
pkgrel=1
arch=(any)
license=('GPL3')
depends=('glibc')
install=glibc-locales.install
source=(60-glibc-locales.hook locale-gen.hook locale-gen locales)
sha256sums=('614416c7ee15dd6f28ce2553f5950546e116c9ea5389df4485f580457379f1c0'
            '1e9a564dbbccba0eca7917396d00aef46e6b6cf31972a34bf7e620dc84156e03'
            '371fbec2b57cb85005eb28df233d0689a71b999127b5c7c40f3fdf978c5909a9'
            '48e0b4240b88d3f117b91a8098e527fcc847a1d9ca90fc30029059c3caa453d2')

package() {
  install -Dm755 "$srcdir/locale-gen" "$pkgdir/usr/lib/glibc-locale/locale-gen"
  for i in $(cat $srcdir/locales); do
      echo "preparing $i.utf8"
      localedef -f UTF-8 -i $i $pkgdir/usr/lib/glibc-locale/$i.utf8
  done
  echo "fixing locales paths"
  mv -v $pkgdir/usr/lib/glibc-locale/aa_ER@saaho.utf8 $pkgdir/usr/lib/glibc-locale/aa_ER.utf8@saaho
  mv -v $pkgdir/usr/lib/glibc-locale/be_BY@latin.utf8 $pkgdir/usr/lib/glibc-locale/be_BY.utf8@latin
  mv -v $pkgdir/usr/lib/glibc-locale/ca_ES@valencia.utf8 $pkgdir/usr/lib/glibc-locale/ca_ES.utf8@valencia
  mv -v $pkgdir/usr/lib/glibc-locale/gez_ER@abegede.utf8 $pkgdir/usr/lib/glibc-locale/gez_ER.utf8@abegede
  mv -v $pkgdir/usr/lib/glibc-locale/gez_ET@abegede.utf8 $pkgdir/usr/lib/glibc-locale/gez_ET.utf8@abegede
  mv -v $pkgdir/usr/lib/glibc-locale/ks_IN@devanagari.utf8 $pkgdir/usr/lib/glibc-locale/ks_IN.utf8@devanagari
  mv -v $pkgdir/usr/lib/glibc-locale/nan_TW@latin.utf8 $pkgdir/usr/lib/glibc-locale/nan_TW.utf8@latin
  mv -v $pkgdir/usr/lib/glibc-locale/sd_IN@devanagari.utf8 $pkgdir/usr/lib/glibc-locale/sd_IN.utf8@devanagari
  mv -v $pkgdir/usr/lib/glibc-locale/sr_RS@latin.utf8 $pkgdir/usr/lib/glibc-locale/sr_RS.utf8@latin
  mv -v $pkgdir/usr/lib/glibc-locale/tt_RU@iqtelif.utf8 $pkgdir/usr/lib/glibc-locale/tt_RU.utf8@iqtelif
  mv -v $pkgdir/usr/lib/glibc-locale/uz_UZ@cyrillic.utf8 $pkgdir/usr/lib/glibc-locale/uz_UZ.utf8@cyrillic
  install -Dm644 "$srcdir/60-glibc-locales.hook" "$pkgdir/usr/share/libalpm/hooks/60-glibc-locales.hook"
  install -Dm644 "$srcdir/locale-gen.hook" "$pkgdir/usr/share/libalpm/hooks/locale-gen.hook"
}