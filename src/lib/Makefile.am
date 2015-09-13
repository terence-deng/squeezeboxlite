SUBDIRS = dsd2pcm

AM_CPPFLAGS = -I/usr/local/include
AM_LDFLAGS = -I/usr/local/lib 

lib_LTLIBRARIES = libsqueezeboxlite.la
libsqueezeboxlite_la_SOURCES = buffer.c dop.c dsd.c ffmpeg.c ir.c output.c output_alsa.c output_pa.c output_pack.c output_stdout.c output_vis.c pcm.c process.c resample.c slimproto.c stream.c utils.c

libsqueezeboxlite_la_SOURCES += faad.c
libsqueezeboxlite_la_SOURCES += flac.c
libsqueezeboxlite_la_SOURCES += decode.c mad.c
libsqueezeboxlite_la_SOURCES += mpg.c
libsqueezeboxlite_la_SOURCES += vorbis.c
libsqueezeboxlite_la_CPPFLAGS = $(AM_CPPFLAGS)

# This library depends on 3rd party libraries
libsqueezeboxlite_la_LIBADD = dsd2pcm/libdsd2pcm.la
libsqueezeboxlite_la_LDFLAGS = -no-undefined -version-info 0:0:0

### Update -version-info above with the following rules
# 1. Start with version information of ‘0:0:0’ for each libtool library.
# 2. Update the version information only immediately before a public release of
#    your software. More frequent updates are unnecessary, and only guarantee
#    that the current interface number gets larger faster.
# 3. If the library source code has changed at all since the last update, then
#    increment revision (‘c:r:a’ becomes ‘c:r+1:a’).
# 4. If any interfaces have been added, removed, or changed since the last
#    update, increment current, and set revision to 0.
# 5. If any interfaces have been added since the last public release, then
#    increment age.
# 6. If any interfaces have been removed or changed since the last public
#    release, then set age to 0.
###

libsqueezeboxlite_la_LIBADD += $(LIBADD_DLOPEN)
libsqueezeboxlite_la_LIBADD += $(LIBM)

if HAVE_PORTAUDIO
libsqueezeboxlite_la_LDFLAGS += -lportaudio
endif

if OS_LINUX
libsqueezeboxlite_la_LDFLAGS += -ldl -lasound -lrt
endif
