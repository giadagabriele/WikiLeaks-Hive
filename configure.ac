#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([hive], [2.9], [jackmc@devlan.net])
AM_INIT_AUTOMAKE([-Wall -Werror foreign])
LT_PREREQ([2.2])
LT_INIT
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_SRCDIR([server/main.c])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AC_PROG_LN_S
AC_PROG_MAKE_SET
AC_PROG_RANLIB

# Checks for libraries.
AC_CHECK_LIB([crypto], [crypt_read])
AC_CHECK_LIB([debug], [debug_print_buffer])
AC_CHECK_LIB([ssl], [aes_crypt_cbc])

# FIXME: Replace `main' with a function in `-lpthread':
#AC_CHECK_LIB([pthread], [main])
# FIXME: Replace `main' with a function in `-lsocket':
#AC_CHECK_LIB([socket], [main])
# FIXME: Replace `main' with a function in `-lutil':
#AC_CHECK_LIB([util], [main])

# Checks for header files.
AC_HEADER_RESOLV
AC_CHECK_HEADERS([arpa/inet.h fcntl.h float.h inttypes.h malloc.h netdb.h netinet/in.h stddef.h stdint.h stdlib.h string.h sys/param.h sys/socket.h sys/time.h unistd.h utime.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_C_INLINE
AC_TYPE_OFF_T
AC_TYPE_SIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T

# Checks for library functions.
AC_FUNC_FORK
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([alarm bzero dup2 gethostbyaddr gethostbyname gethostname gettimeofday inet_ntoa memmove memset select socket strcasecmp strchr strdup strerror strrchr strstr strtoul utime])

AC_CONFIG_FILES([Makefile
                 client/Makefile
                 client/cryptcat/Makefile
                 client/ctHive/ILMSDK/makefile
                 common/bzip2-1.0.6/Makefile
                 common/crypto/Makefile
                 common/debug/Makefile
                 common/ssllibrary/Makefile
                 common/strings/Makefile
                 ilm-client/Makefile])
AC_CONFIG_SUBDIRS([server client common/bzip2 common/crypto common/debug common/ssl common/strings])
AC_OUTPUT
