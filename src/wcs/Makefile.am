sexwcsdir = $(includedir)/sextractor/wcs
sexwcs_HEADERS = \
	cel.h lin.h poly.h proj.h sph.h tnx.h wcs.h \
	wcsmath.h wcstrig.h

noinst_LTLIBRARIES = libsexwcs.la
libsexwcs_la_SOURCES = \
	$(sexwcs_HEADERS) \
	cel.c lin.c poly.c proj.c sph.c tnx.c wcs.c \
	wcstrig.c

CLEANFILES = *~
MAINTAINERCLEANFILES = \
	Makefile.in \
	stamp-* *.new
