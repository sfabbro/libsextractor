AC_INIT([libsextractor],[2.4.4.3],[E.Bertin and Poloka Team])
AC_CONFIG_SRCDIR(src/makeit.c)
AC_CONFIG_AUX_DIR(autoconf)
AM_CONFIG_HEADER(config.h)
AM_INIT_AUTOMAKE
date=`date +%Y-%m-%d`
date2=`date +"%a %b %d %Y"`
date3=`date +"%B %Y"`
AC_DEFINE_UNQUOTED(DATE, "$date", [Archive creation date])

# Checks for programs.
AC_PROG_CC
# C Compiler: Check that it is ANSI C
AM_PROG_CC_STDC
# C Compiler: Check that it is POSIX-compliant
AC_SEARCH_LIBS([strerror],[cposix])

# those 2 define avoid checks of c++ and fortran during AC_PROG_LIBTOOL
define([AC_LIBTOOL_LANG_CXX_CONFIG], [:])
define([AC_LIBTOOL_LANG_F77_CONFIG], [:])
LT_INIT([disable-static])

# Checks for libraries.
AC_CHECK_LIB(m, sin)

# Checks for header files.
AC_HEADER_STDC
AC_CHECK_HEADERS([fcntl.h limits.h malloc.h stdlib.h string.h sys/mman.h sys/types.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_TYPE_OFF_T
AC_TYPE_SIZE_T
AC_STRUCT_TM
AC_TYPE_UID_T

# Checks for library functions.
AC_FUNC_ERROR_AT_LINE
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_DIAGNOSE([obsolete],[your code may safely assume C89 semantics that RETSIGTYPE is void.
Remove this warning and the `AC_CACHE_CHECK' when you adjust the code.])dnl
AC_CACHE_CHECK([return type of signal handlers],[ac_cv_type_signal],[AC_COMPILE_IFELSE(
[AC_LANG_PROGRAM([#include <sys/types.h>
#include <signal.h>
],
		 [return *(signal (0, 0)) (0) == 1;])],
		   [ac_cv_type_signal=int],
		   [ac_cv_type_signal=void])])
AC_DEFINE_UNQUOTED([RETSIGTYPE],[$ac_cv_type_signal],[Define as the return type of signal handlers
		    (`int' or `void').])

AC_FUNC_STAT
AC_FUNC_STRFTIME
AC_CHECK_FUNCS([atexit memcpy memmove memset mkdir munmap strstr])

# Check support for large files
AC_SYS_LARGEFILE
AC_FUNC_FSEEKO

# cflags forced -O1 for now, since it seems buggy with sextractor 2.4.4
# might be a gcc bug, to check with later versions of gcc and SExtractor
# replace any -Ox by -O1
new_cflags=""
for flag in $CFLAGS; do
    case $flag in
        -O0) flag=-O0 ;;
	-O*) flag=-O1 ;;	
    esac	
    new_cflags="$new_cflags $flag"
done
CFLAGS="$new_cflags"

AC_CONFIG_FILES([Makefile man/Makefile src/Makefile src/fits/Makefile src/wcs/Makefile sextractor.pc man/sexmain.1])
AC_OUTPUT
