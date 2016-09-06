################################################################################
# perl-algorithm-diff
################################################################################

# Package Version/Information
pkgname=perl-algorithm-diff
_dist=Algorithm-Diff
pkgver=1.1903
pkgrel=1
pkgdesc="Algorithm::Diff - Compute 'intelligent' differences between two files / lists"

# System Requirements
arch=('x86_64')
depends=(perl)

# Misc. Details
url="https://metacpan.org/release/${_dist}"
license=('GPL' 'PerlArtistic')
options=('!emptydirs' purge)

# Source and Checksums
source=(
  http://search.cpan.org/CPAN/authors/id/T/TY/TYEMQ/${_dist}-${pkgver}.tar.gz
)
md5sums=(
  '0e8add21a641b8d66436df0c2024bf3b'
)

################################################################################
# Build/Check/Package
################################################################################

build() {
  cd "${srcdir}/${_dist}-${pkgver}"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  export PERL_MM_USE_DEFAULT=1 PERL_AUTOINSTALL=--skipdeps
  /usr/bin/perl Makefile.PL
  make
}

check() {
  cd "${srcdir}/${_dist}-${pkgver}"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  export PERL_MM_USE_DEFAULT=1
  make test
}

package() {
  cd "${srcdir}/${_dist}-${pkgver}"
  unset PERL5LIB PERL_MM_OPT PERL_LOCAL_LIB_ROOT
  make install INSTALLDIRS=vendor DESTDIR="${pkgdir}"
}
