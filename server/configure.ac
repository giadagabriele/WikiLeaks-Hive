#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([hived], [2.9])
AM_INIT_AUTOMAKE([-Wall, -Werror])
#LT_PREREQ([2.2])
#LT_INIT

AC_LANG([C])

AC_CONFIG_FILES([Makefile])
AC_CONFIG_SRCDIR([launchshell.h])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CC
AC_PROG_MAKE_SET

#Configuration Options
# --enable-debug[=no]
AC_ARG_ENABLE([debug],
	[AS_HELP_STRING([--enable-debug], [enable debug code (default is no)])],
	[debug="$withval"], [debug=no])

ACX_PTHREAD(
	[AC_DEFINE( [HAVE_PTHREAD], [1], [Define if you have POSIX threads libaries and header files.] )
		LIBS="$PTHREAD_LIBS $LIBS"
		CFLAGS="$CFLAGS $PTHREAD_CFLAGS"
		CC="$PTHREAD_CC"])

# Checks for libraries.
AC_CHECK_LIB([bzip2], [BZ2_bzBuffToBuffCompress])
AC_CHECK_LIB([crypto], [crypt_read], , , [pthread, util])
AC_CHECK_LIB([debug], [debug_print_buffer])
AC_CHECK_LIB([ssl], [aes_crypt_ctr])
AC_CHECK_LIB([strings], [cl_string])

# Checks for header files.
AC_CHECK_HEADERS([arpa/inet.h fcntl.h inttypes.h limits.h netdb.h netinet/in.h stddef.h stdint.h stdlib.h string.h sys/ioctl.h sys/param.h sys/socket.h sys/time.h termios.h unistd.h utime.h utmpx.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_TYPE_PID_T
AC_TYPE_SIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT8_T

# Checks for library functions.
AC_FUNC_FORK
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([alarm dup2 memset select socket strerror strstr utime])

AC_OUTPUT

printf "\n$PACKAGE_NAME-$target-$PACKAGE_VERSION\n\n"
printf "Debug Build: $debug\n"
printf " C Compiler: $CC $CFLAGS\n"
printf "     Linker: $LD $LDFLAGS $LIBS\n"
