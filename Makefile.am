AUTOMAKE_OPTIONS	= foreign no-dependencies
SUBDIRS			= src
EXTRA_DIST		= config doc AUTHORS BUGS ChangeLog COPYING HISTORY \
			  INSTALL README THANKS README.libsex

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = sex.pc

CLEANFILES = *~
MAINTAINERCLEANFILES = \
	aclocal.m4 \
	configure \
	Makefile.in \
	config.h \
	config.h.in \
	autoconf/* \
	autoconf \
	autom4te.cache*
