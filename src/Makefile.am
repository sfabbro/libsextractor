SUBDIRS	= fits wcs
lib_LTLIBRARIES	= libsex.la

sexdir = $(includedir)/sex
sex_HEADERS = \
	assoc.h astrom.h back.h bpro.h check.h clean.h \
	define.h extract.h field.h filter.h flag.h \
	globals.h growth.h image.h interpolate.h key.h \
	neurro.h param.h photom.h plist.h poly.h prefs.h \
	preflist.h psf.h retina.h sexhead1.h sexhead.h \
	sexheadsc.h som.h types.h weight.h winpos.h

libsex_la_SOURCES = \
	$(sex_HEADERS) \
	analyse.c assoc.c astrom.c back.c bpro.c catout.c \
	check.c clean.c extract.c field.c filter.c \
	flag.c graph.c growth.c image.c interpolate.c \
	main.c makeit.c manobjlist.c misc.c neurro.c pc.c \
	photom.c plist.c prefs.c psf.c readimage.c \
	refine.c retina.c scan.c som.c weight.c winpos.c

# forced -O1 for now, since it seems buggy with above.
# might be a gcc bug, to check with later versions of gcc and SExtractor
libsex_la_CFLAGS = -O1
libsex_la_CPPFLAGS = -I$(top_srcdir)/src/wcs
libsex_la_LIBADD = \
	$(top_builddir)/src/fits/libsexfits.la \
	$(top_builddir)/src/wcs/libsexwcs.la

# keep sexmain as exec name to allow standard SExtractor exec to cohabit
bin_PROGRAMS = sexmain
sexmain_SOURCES = main.c
sexmain_LDADD = libsex.la

CLEANFILES = *~
MAINTAINERCLEANFILES = \
	Makefile.in \
	stamp-* *.new
