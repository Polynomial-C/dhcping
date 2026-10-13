AC_INIT([dhcping], [1.5])
AC_CONFIG_SRCDIR([dhcping.c])
AM_INIT_AUTOMAKE([foreign])

AC_PROG_CC
AC_PROG_INSTALL

dnl
dnl some libs sunos/solaris needs
dnl
AC_CANONICAL_TARGET
AS_CASE([$target_os],
[sunos*], [
        AC_DEFINE(SUNOS)
	AC_CHECK_LIB(socket,main)
	AC_CHECK_LIB(nsl,main)
	AC_CHECK_LIB(resolv,main)
	OS_OPT=
	AC_SUBST(OS_OPT)
],
[solaris*], [
        AC_DEFINE(SUNOS)
	AC_CHECK_LIB(socket,main)
	AC_CHECK_LIB(nsl,main)
	AC_CHECK_LIB(resolv,main)
	OS_OPT=
	AC_SUBST(OS_OPT)
])

AC_CHECK_HEADERS([netdb.h netinet/in.h stdlib.h string.h sys/socket.h sys/time.h unistd.h])

AC_CHECK_FUNCS([gethostbyname memset select socket])

AC_CONFIG_FILES([Makefile version.h])
AC_OUTPUT
