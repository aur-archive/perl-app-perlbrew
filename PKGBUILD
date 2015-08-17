# Contributor: AUR Perl <aurperl@juster.info>
# Generator  : CPANPLUS::Dist::Arch 1.18

pkgname='perl-app-perlbrew'
pkgver='0.28'
pkgrel='1'
pkgdesc="Manage perl installations in your \$HOME"
arch=('any')
license=('PerlArtistic' 'GPL')
options=('!emptydirs')
depends=('perl>=5.008' 'perl-devel-patchperl>=0.26' 'perl-file-path-tiny')
makedepends=('perl-io-all' 'perl-path-class' 'perl-test-exception' 'perl-test-output' 'perl-test-spec')
url='http://search.cpan.org/dist/App-perlbrew'
source=('http://search.cpan.org/CPAN/authors/id/G/GU/GUGOD/App-perlbrew-0.28.tar.gz')
md5sums=('f1c4dd8dca73b0338c896b4a56e112d9')
sha512sums=('866e074b69a988ca98359e220ab715d6a0484f3ca6f82a33d05f373ba62ee871c97d4ec0ec7e09b8122c1d656475d2806a5b39ba0e2fa9ef7cd7bfb8816ee757')
_distdir="${srcdir}/App-perlbrew-0.28"

build() {
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""                 \
      PERL_AUTOINSTALL=--skipdeps                            \
      PERL_MM_OPT="INSTALLDIRS=vendor DESTDIR='$pkgdir'"     \
      PERL_MB_OPT="--installdirs vendor --destdir '$pkgdir'" \
      MODULEBUILDRC=/dev/null

    cd "$_distdir"
    /usr/bin/perl Makefile.PL
    make
  )
}

check() {
  cd "$_distdir"
  ( export PERL_MM_USE_DEFAULT=1 PERL5LIB=""
    make test
  )
}

package() {
  cd "$_distdir"
  make install
  find "$pkgdir" -name .packlist -o -name perllocal.pod -delete
}

# Local Variables:
# mode: shell-script
# sh-basic-offset: 2
# End:
# vim:set ts=2 sw=2 et:
