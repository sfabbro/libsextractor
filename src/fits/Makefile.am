sexfits_HEADERS = \
	fitscat_defs.h fitscat.h
sexfitsdir = $(includedir)/sextractor/fits

noinst_LTLIBRARIES = libsexfits.la
libsexfits_la_SOURCES = \
	$(sexfits_HEADERS) \
	fitsbody.c fitscat.c fitscheck.c fitscleanup.c \
	fitsconv.c fitshead.c fitskey.c fitsmisc.c \
	fitsread.c fitstab.c fitsutil.c fitswrite.c

CLEANFILES = *~
MAINTAINERCLEANFILES = \
	Makefile.in \
	stamp-* *.new
