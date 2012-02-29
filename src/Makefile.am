SUBDIRS	= fits wcs
lib_LTLIBRARIES	= libsextractor.la

sextractordir = $(includedir)/sextractor
sextractor_HEADERS = \
	assoc.h astrom.h back.h bpro.h check.h clean.h \
	define.h extract.h field.h filter.h flag.h \
	globals.h growth.h image.h interpolate.h key.h \
	neurro.h param.h photom.h plist.h poly.h prefs.h \
	preflist.h psf.h retina.h sexhead1.h sexhead.h \
	sexheadsc.h som.h types.h weight.h winpos.h

libsextractor_la_SOURCES = \
	$(sextractor_HEADERS) \
	analyse.c assoc.c astrom.c back.c bpro.c catout.c \
	check.c clean.c extract.c field.c filter.c \
	flag.c graph.c growth.c image.c interpolate.c \
	main.c makeit.c manobjlist.c misc.c neurro.c pc.c \
	photom.c plist.c prefs.c psf.c readimage.c \
	refine.c retina.c scan.c som.c weight.c winpos.c

libsextractor_la_CPPFLAGS = -I$(top_srcdir)/src/wcs
libsextractor_la_LIBADD = \
	$(top_builddir)/src/fits/libsexfits.la \
	$(top_builddir)/src/wcs/libsexwcs.la

# rename sexmain as exec name to avoid collision file names with SExtractor
bin_PROGRAMS = sexmain
sexmain_SOURCES = main.c
sexmain_LDADD = libsextractor.la

CLEANFILES = *~
MAINTAINERCLEANFILES = \
	Makefile.in \
	stamp-* *.new
