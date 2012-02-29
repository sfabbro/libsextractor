AUTOMAKE_OPTIONS	= foreign no-dependencies
SUBDIRS			= src man
EXTRA_DIST		= config doc AUTHORS BUGS ChangeLog COPYING HISTORY \
			  INSTALL README THANKS README.libsextractor

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = sextractor.pc

CLEANFILES = *~
MAINTAINERCLEANFILES = \
	aclocal.m4 \
	configure \
	Makefile.in \
	config.h \
	config.h.in \
	autoconf* \
	autom4te.cache*
