#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.69)
AC_INIT(squeezeboxlite, 1.0.0, dengtooling@gmail.com)
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_SRCDIR(src/squeezeboxlite.c)
AC_CONFIG_HEADERS(config.h)
AM_INIT_AUTOMAKE(foreign)

# Checks for programs.
AC_PROG_CC
AC_PROG_LIBTOOL

# Checks for libraries.
LT_LIB_M
AC_CHECK_LIB([pthread],[pthread_create])
AC_CHECK_LIB([asound], [snd_pcm_open], [have_libasound=1], [have_libasound=0])
AC_CHECK_LIB([faad],[NeAACDecOpen])
AC_CHECK_LIB([FLAC],[FLAC__stream_decoder_init_stream])
AC_CHECK_LIB([mad],[mad_decoder_run])
AC_CHECK_LIB([mpg123],[mpg123_init])
AC_CHECK_LIB([portaudio], [Pa_Initialize], [have_portaudio=1], [have_portaudio=0])

# Checks for header files.
AC_CHECK_HEADERS(arpa/inet.h fcntl.h limits.h malloc.h netdb.h netinet/in.h stddef.h stdlib.h string.h sys/ioctl.h sys/socket.h sys/time.h unistd.h)
AC_CHECK_HEADERS(alsa/asoundlib.h)
AC_CHECK_HEADERS([neaacdec.h],[],AC_MSG_ERROR([neaacdec.h not found]))
AC_CHECK_HEADERS([FLAC/stream_decoder.h],[],AC_MSG_ERROR([FLAC/stream_decoder.h not found]))
AC_CHECK_HEADERS([mad.h],[],AC_MSG_ERROR([mad.h not found]))
AC_CHECK_HEADERS([mpg123.h],[],AC_MSG_ERROR([mpg123.h not found]))
AC_CHECK_HEADERS([vorbis/vorbisfile.h],[],AC_MSG_ERROR([vorbis/vorbisfile.h not found]))

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.
AC_FUNC_ALLOCA
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_CHECK_FUNCS([clock_gettime floor ftruncate gettimeofday inet_ntoa memmove memset pow realpath select socket strchr strerror strstr strtoul])

# Custom check for os, similar to webkit
AC_MSG_CHECKING([for native Win32])
case "$host" in
     *-*-mingw*)
       os_win32=yes
       ;;
     *)
       os_win32=no
       ;;
esac
AC_MSG_RESULT([$os_win32])

case "$host" in
     *-*-linux*)
       os_linux=yes
       ;;
     *-*-freebsd*)
       os_freebsd=yes
       ;;
     *-*-darwin*)
       os_darwin=yes
       ;;
esac
case "$host_os" in
     gnu* | linux* | k*bsd*-gnu)
       os_gnu=yes
       ;;
     *)
       os_gnu=no
       ;;
esac

# OS conditionals
AM_CONDITIONAL([OS_WIN32],[test "$os_win32" = "yes"])
AM_CONDITIONAL([OS_UNIX],[test "$os_win32" = "no"])
AM_CONDITIONAL([OS_LINUX],[test "$os_linux" = "yes"])
AM_CONDITIONAL([OS_GNU],[test "$os_gnu" = "yes"])
AM_CONDITIONAL([OS_FREEBSD],[test "$os_freebsd" = "yes"])

# Custom check for libportaudio
AM_CONDITIONAL([HAVE_PORTAUDIO], [test "$have_portaudio" -eq 1])


AC_OUTPUT(Makefile
	  src/Makefile
	  src/lib/Makefile
	  src/lib/dsd2pcm/Makefile)
