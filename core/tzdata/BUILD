pkgname=tzdata
pkgver=2017b
pkgdesc="Timezone data"
license=(Unlicense)

timezones=('africa' 'antarctica' 'asia' 'australasia'
           'europe' 'northamerica' 'southamerica'
           'pacificnew' 'etcetera' 'backward'
           'systemv' 'factory')
prepare() {
  cd "$srcdir"
  wget -qO- "https://www.iana.org/time-zones/repository/releases/${pkgname}${pkgver}.tar.gz"  | tar zxf -
}

package() {
  cd "${srcdir}"
  zic -y ./yearistype -d "${pkgdir}"/usr/share/zoneinfo ${timezones[@]}
  zic -y ./yearistype -d "${pkgdir}"/usr/share/zoneinfo/posix ${timezones[@]}
  zic -y ./yearistype -d "${pkgdir}"/usr/share/zoneinfo/right -L leapseconds ${timezones[@]}
  
  zic -y ./yearistype -d "${pkgdir}"/usr/share/zoneinfo -p America/New_York
  install -m444 -t "${pkgdir}"/usr/share/zoneinfo iso3166.tab zone1970.tab zone.tab # zone.tab is depricated and will go soon
}
