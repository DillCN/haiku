# Generated automatically from Makefile.in by configure.
# Main makefile for GNU Shar utility package.
# Copyright (C) 1995 Free Software Foundation, Inc.
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2, or (at your option)
# any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA 02111-1307, USA.

PACKAGE = sharutils
VERSION = 4.2.1

SHELL = /bin/sh


srcdir = .

DISTFILES = COPYING AUTHORS BACKLOG ChangeLog ChangeLog.OLD INSTALL \
Makefile.in ABOUT-NLS NEWS README README.OLD THANKS TODO \
acconfig.h aclocal.m4 config.h.in configure configure.in install-sh \
mkinstalldirs stamp-h.in README-alpha

SUBDIRS = doc lib po intl src checks contrib

all: all-recursive

all-recursive install install-exec install-data uninstall TAGS ID \
mostlyclean-recursive clean-recursive distclean-recursive \
maintainer-clean-recursive check: config.h Makefile
	for subdir in $(SUBDIRS); do \
	  target=`echo $@|sed 's/-recursive//'`; \
	  echo making $$target in $$subdir; \
	  (cd $$subdir && $(MAKE) $$target) \
	    || case "$(MFLAGS)" in *k*) fail=yes;; *) exit 1;; esac; \
	done && test -z "$$fail"

install-man: config.h Makefile
	echo making $@ in doc
	cd doc && $(MAKE) $@

distdir = $(PACKAGE)-$(VERSION)
dist: Makefile
	rm -fr $(distdir)
	mkdir $(distdir)
	for file in $(DISTFILES); do \
	  ln $(srcdir)/$$file $(distdir) 2> /dev/null \
	    || cp -p $(srcdir)/$$file $(distdir); \
	done
	for subdir in $(SUBDIRS); do \
	  mkdir $(distdir)/$$subdir || exit 1; \
	  (cd $$subdir && $(MAKE) $@) || exit 1; \
	done
	tar zchovf $(distdir).tar.gz $(distdir)
	rm -fr $(distdir)

tags: TAGS
id: ID

mostlyclean: mostlyclean-recursive mostlyclean-local

clean: clean-recursive clean-local

distclean: distclean-recursive distclean-local
	rm -f config.status

maintainer-clean: maintainer-clean-recursive maintainer-clean-local
	@echo "This command is intended for maintainers to use;"
	@echo "it deletes files that may require special tools to rebuild."
	rm -f config.status

mostlyclean-local:

clean-local: mostlyclean-local

distclean-local: clean-local
	rm -f Makefile config.cache config.h config.log stamp-h tupdate.perl

maintainer-clean-local: distclean-local

check:

dvi info:
	cd doc && $(MAKE) $@

# For understanding the following see the autoconf manual.
configure: configure.in aclocal.m4
	cd $(srcdir) && autoconf

# autoheader might not change config.h.in
config.h.in: stamp-h.in
stamp-h.in: configure.in acconfig.h
	cd $(srcdir) && autoheader
	rm -f $(srcdir)/stamp-h.in && echo timestamp > $(srcdir)/stamp-h.in

#config.status might not change config.h
# Don't rerun config.status if we just configured.
config.h: stamp-h
stamp-h: config.h.in config.status
	test ! -f stamp-h || ./config.status
	rm -f stamp-h && echo timestamp > stamp-h

Makefile: Makefile.in config.status
	./config.status

config.status: configure config.h.in
	./config.status --recheck

# Tell versions [3.59,3.63) of GNU make not to export all variables.
# Otherwise a system limit (for SysV at least) may be exceeded.
.NOEXPORT:
