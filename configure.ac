dnl 
dnl  Copyright © 2003 Keith Packard, Noah Levitt
dnl 
dnl  Permission to use, copy, modify, distribute, and sell this software and its
dnl  documentation for any purpose is hereby granted without fee, provided that
dnl  the above copyright notice appear in all copies and that both that
dnl  copyright notice and this permission notice appear in supporting
dnl  documentation, and that the name of Keith Packard not be used in
dnl  advertising or publicity pertaining to distribution of the software without
dnl  specific, written prior permission.  Keith Packard makes no
dnl  representations about the suitability of this software for any purpose.  It
dnl  is provided "as is" without express or implied warranty.
dnl 
dnl  KEITH PACKARD DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE,
dnl  INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS, IN NO
dnl  EVENT SHALL KEITH PACKARD BE LIABLE FOR ANY SPECIAL, INDIRECT OR
dnl  CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE,
dnl  DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER
dnl  TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
dnl  PERFORMANCE OF THIS SOFTWARE.
dnl
dnl Process this file with autoconf to create configure.

AC_PREREQ([2.57])

AC_INIT(libXTrap, 1.0.1, [https://bugs.freedesktop.org/enter_bug.cgi?product=xorg], libXTrap)
AM_INIT_AUTOMAKE([foreign dist-bzip2])

# Require xorg-macros: XORG_COMPILER_FLAGS, XORG_CHANGELOG
m4_ifndef([XORG_MACROS_VERSION], [AC_FATAL([must install xorg-macros 1.17 or later before running autoconf/autogen])])
XORG_MACROS_VERSION(1.17)
AC_CONFIG_HEADERS([config.h])

# Check for progs
AC_PROG_CC
AC_PROG_LIBTOOL
XORG_COMPILER_FLAGS

# Check for dependencies
PKG_CHECK_MODULES(XTRAP, x11 xt trapproto xext xextproto)
XTRAP_CFLAGS="$BASE_CFLAGS $XTRAP_CFLAGS"
AC_SUBST(XTRAP_CFLAGS)
AC_SUBST(XTRAP_LIBS)

XORG_RELEASE_VERSION
XORG_CHANGELOG

AC_OUTPUT([Makefile
	   src/Makefile
           xtrap.pc])

