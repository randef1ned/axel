bin_PROGRAMS = axel
axel_SOURCES = \
	compat-android.h \
	compat-bsd.h \
	compat-ssl.h \
	compat-win32.h \
	src/abuf.c \
	src/abuf.h \
	src/axel.c \
	src/axel.h \
	src/sleep.h \
	src/sleep.c \
	src/conf.c \
	src/conf.h \
	src/conn.c \
	src/conn.h \
	src/ftp.c \
	src/ftp.h \
	src/hash.c \
	src/hash.h \
	src/http.c \
	src/http.h \
	src/random.c \
	src/search.c \
	src/search.h \
	src/ssl.h \
	src/tcp.c \
	src/tcp.h \
	src/text.c

axel_CFLAGS = $(AM_CFLAGS) $(PTHREAD_CFLAGS)
AM_CFLAGS = $(WARN_CFLAGS) \
	-Wno-declaration-after-statement \
	-Wno-error=cast-align \
	-Wno-error=inline

if WITH_SSL
axel_SOURCES += \
	src/dn-match.c \
	src/ssl.c \
	src/ssl_verify.c
AM_CFLAGS += $(SSL_CFLAGS)
endif

axel_LDADD = $(LIBOBJS) $(SSL_LIBS) $(LIBINTL) $(PTHREAD_LIBS)
axel_CC = $(PTHREAD_CC)

AM_CPPFLAGS = -DLOCALEDIR=\""$(localedir)"\"
AM_CPPFLAGS += -D_BSD_SOURCE -D_DEFAULT_SOURCE
