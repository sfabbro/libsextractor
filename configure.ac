AC_INIT(libsex, 2.4.4.3, [E.Bertin and Poloka Team])
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
AC_ISC_POSIX
AC_DISABLE_STATIC
# those 2 define avoid checks of c++ and fortran during AC_PROG_LIBTOOL
define([AC_LIBTOOL_LANG_CXX_CONFIG], [:])
define([AC_LIBTOOL_LANG_F77_CONFIG], [:])
AC_PROG_LIBTOOL

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
AC_TYPE_SIGNAL
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

AC_CONFIG_FILES([Makefile man/Makefile src/Makefile src/fits/Makefile src/wcs/Makefile sex.pc man/sex.1])
AC_OUTPUT
