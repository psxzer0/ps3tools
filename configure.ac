#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.66])
AC_INIT([ps3tools], [0.1], [])
AC_CONFIG_SRCDIR([tools.c])
AC_CONFIG_HEADERS([config.h])
AM_INIT_AUTOMAKE([-Wall])

# Checks for programs.
AC_PROG_CC

# Checks for libraries.
AC_CHECK_LIB([gmp], [__gmpz_init], [GMP_LIBS="-lgmp"], [GMP_LIBS=""])
AC_CHECK_LIB([z], [inflate])

AC_SUBST(GMP_LIBS)
AM_CONDITIONAL(HAVE_LIBGMP, test "$GMP_LIBS" != "")


dnl use pretty build output with automake >= 1.11
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])],
  [AM_DEFAULT_VERBOSITY=1
   AC_SUBST(AM_DEFAULT_VERBOSITY)])


# Checks for header files.
AC_CHECK_HEADERS([arpa/inet.h fcntl.h inttypes.h limits.h stdint.h stdlib.h string.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_INLINE
AC_TYPE_OFF_T
AC_TYPE_SIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_FUNC_REALLOC
AC_CHECK_FUNCS([getpagesize memset strrchr strstr strtoul strtoull])

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
