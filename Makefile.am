SUBDIRS = docs po .

EXTRA_DIST = configure.in.in configure.in Makefile.cvs bibletime.m4 README

btadmindir = $(top_srcdir)/admin

EXTRA_DIST += $(btadmindir)/compile
EXTRA_DIST += $(btadmindir)/config.guess
EXTRA_DIST += $(btadmindir)/config.pl
EXTRA_DIST += $(btadmindir)/config.sub
EXTRA_DIST += $(btadmindir)/configure.in.bot.end
EXTRA_DIST += $(btadmindir)/configure.in.min
EXTRA_DIST += $(btadmindir)/cvs-clean.pl
EXTRA_DIST += $(btadmindir)/install-sh
EXTRA_DIST += $(btadmindir)/ltmain.sh
EXTRA_DIST += $(btadmindir)/missing
EXTRA_DIST += $(btadmindir)/mkinstalldirs
EXTRA_DIST += $(btadmindir)/ylwrap
EXTRA_DIST += $(btadmindir)/Makefile.common
EXTRA_DIST += $(btadmindir)/acinclude.m4.in
EXTRA_DIST += $(btadmindir)/am_edit
EXTRA_DIST += $(btadmindir)/conf.change.pl
EXTRA_DIST += $(btadmindir)/debianrules
EXTRA_DIST += $(btadmindir)/depcomp
EXTRA_DIST += $(btadmindir)/detect-autoconf.sh
EXTRA_DIST += $(btadmindir)/libtool.m4.in
EXTRA_DIST += $(btadmindir)/nmcheck
EXTRA_DIST += $(btadmindir)/cvs.sh


# not a GNU package. You can remove this line, if
# have all needed files, that a GNU package needs
AUTOMAKE_OPTIONS = 1.6 foreign dist-bzip2

$(top_srcdir)/acinclude.m4: $(top_srcdir)/admin/acinclude.m4.in $(top_srcdir)/admin/libtool.m4.in bibletime.m4
	@cd $(top_srcdir) && cat admin/acinclude.m4.in admin/libtool.m4.in bibletime.m4 > acinclude.m4
$(top_srcdir)/configure.in: $(top_srcdir)/configure.files $(shell test -f $(top_srcdir)/configure.files && cat $(top_srcdir)/configure.files)
	cd $(top_srcdir) && $(MAKE) -f admin/Makefile.common configure.in
$(top_srcdir)/subdirs:
	cd $(top_srcdir) && $(MAKE) -f admin/Makefile.common subdirs
$(top_srcdir)/configure.files:
	cd $(top_srcdir) && $(MAKE) -f admin/Makefile.common configure.files

MAINTAINERCLEANFILES = configure.files subdirs 

dist-hook:	
	rm -f $(distdir)/bibletime-*.tar.gz $(distdir)/bibletime-*.tar.bz2
	rm -rf `find $(distdir) -name tags -o -name TAGS -o -name \*.xcf`
	rm -rf $(distdir)/autom4te.cache

