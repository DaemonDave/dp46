# $Id: configure.ac,v 1.16 2008/12/02 21:28:54 cvsuser Exp $
# configure.ac

# Library Version Master Version DO NOT TOUCH
MAJORVERSION=0
MINORVERSION=1
REVISION=0
VER='${MAJORVERSION}:${MINORVERSION}:${REVISION}'
#
AC_PREREQ(2.6)
AC_INIT([libdp46], [[${VER}]], [david.erickson@drdc-rddc.gc.ca])
AC_CONFIG_SRCDIR([PanTiltMessage.c])
AC_CONFIG_MACRO_DIR([m4])
# determine system type by conventional m4 macro
AC_CANONICAL_TARGET
# Get the date timestamp for library / documentation version control
DATE=$(date)
AC_SUBST(DATE) 
# determine target operating system for library compilation
# carried out by drdc-target-prefix.m4 file in aclocal
TARGET_PREFIX

AM_INIT_AUTOMAKE([-Wall -Werror foreign])


AC_SUBST(MAJORVERSION)
AC_SUBST(MINORVERSION)
AC_SUBST(REVISION)

REL_VER=${REVISION}
LIB_VER=${MAJORVERSION}.${MINORVERSION}-${REVISION}
#          |               |                 |
#   +------+               |                 +----+
#   |                      |                      |
#  current    :         revision     :  		  		age
#   |                      |                      |
#   |                      |                      +- increment if interfaces have been added
#   |                      |                         set to zero if interfaces have been removed
#   |                      |                         or changed
#   |                      +- increment if source code has changed
#   |                         set to zero if current is incremented
#   +- increment if interfaces have been added, removed or changed
AC_SUBST(LIB_VER)
AC_SUBST(REL_VER)
PKG_PROG_PKG_CONFIG

# Checks for programs.
AC_PROG_CC
AC_PROG_CC_STDC
AC_PROG_CXX
AC_PROG_LIBTOOL
AM_PROG_CC_C_O
AM_PROG_AR

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h stdlib.h string.h termios.h unistd.h])
# check for standard C headers
AC_CHECK_HEADER([math.h])
AC_CHECK_HEADER([stdio.h])
AC_CHECK_HEADER([stdlib.h])
AC_CHECK_HEADER([assert.h])
AC_CHECK_HEADER([time.h])
AC_CHECK_HEADER([signal.h])
# check for kernel headers
AC_CHECK_HEADER([setjmp.h])
# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_SIZE_T
# Checks for library functions.
# Checks for libraries.
# FIXME: Replace `main' with a function in `-lm':
AC_CHECK_LIB([m], [main])
# try to find libray in usual spaces
AC_CHECK_LIB([m],[fabs],[],[echo fabs not found] )
AC_CHECK_LIB([rt], [timer_create])
# output phase - puts  results into files
AC_CONFIG_HEADER(config.h)
AC_CONFIG_FILES([Makefile])
AC_OUTPUT
