#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.69)
AC_INIT([PythonMagick],[0.9.14],[],[PythonMagick])
AC_CONFIG_SRCDIR([pythonmagick_src/_PathLinetoAbs.cpp])
AC_CONFIG_AUX_DIR([config])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_LIBOBJ_DIR([pythonmagick_src])
AC_CONFIG_HEADERS([config/config.h])
AC_CONFIG_FILES([Makefile
                 helpers_src/Makefile
                 pythonmagick_src/Makefile])

# Ensure that make can run correctly
AM_SANITY_CHECK

AM_INIT_AUTOMAKE([1.12 color-tests foreign parallel-tests silent-rules subdir-objects dist-bzip2 dist-lzip dist-xz dist-zip])

# Enable support for silent build rules
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET
AC_PROG_LIBTOOL
AM_PATH_PYTHON([2.4])
PKG_PROG_PKG_CONFIG

# Add configure option --enable-maintainer-mode which enables dependency
# checking and generation useful to package maintainers.  This is made an
# option to avoid confusing end users.
AM_MAINTAINER_MODE

# Checks for libraries.
AX_BOOST_BASE
AX_BOOST_PYTHON

PKG_CHECK_MODULES( MAGICKCORE, [MagickCore >= 6.8.6])
PKG_CHECK_MODULES( MAGICKPP, [Magick++ >= 6.8.6])
AC_SUBST(MAGICKPP_CFLAGS)
AC_SUBST(MAGICKPP_LIBS)
AC_SUBST(MAGICKCORE_CFLAGS)
AC_SUBST(MAGICKCORE_LIBS)
# Checks for header files.

# Checks for typedefs, structures, and compiler characteristics.
AC_HEADER_STDBOOL
AC_C_CONST
AC_TYPE_SIZE_T

CXXFLAGS="$CXXFLAGS -DBOOST_PYTHON_DYNAMIC_LIB $PYTHON_CPPFLAGS"

# Checks for library functions.

AC_OUTPUT
