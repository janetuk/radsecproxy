AUTOMAKE_OPTIONS = foreign
ACLOCAL_AMFLAGS = -I m4

SUBDIRS = radius include . examples
DIST_SUBDIRS=tests ${SUBDIRS}


INCLUDES = -I$(srcdir)/include -I$(srcdir)/radsecproxy-includes
AM_CFLAGS = -Wall -g

lib_LTLIBRARIES = libradsec.la

libradsec_la_SOURCES = \
	avp.c \
	compat.c \
	conf.c \
	conn.c \
	debug.c \
	err.c \
	event.c \
	packet.c \
	peer.c \
	radsec.c \
	request.c \
	send.c \
	tcp.c \
	udp.c

libradsec_la_SOURCES += \
	rsp_debug.c \
	rsp_hash.c \
	rsp_list.c \
	rsp_util.c

if RS_ENABLE_TLS
libradsec_la_SOURCES += \
	tls.c \
	rsp_tlscommon.c
endif

libradsec_la_SOURCES += compat.h \
	conn.h \
	debug.h \
	err.h \
	event.h \
	packet.h \
	peer.h \
	rsp_debug.h\
	rsp_hash.h \
	rsp_list.h \
	rsp_tlscommon.h \
	rsp_util.h \
	tcp.h \
	tls.h \
	udp.h

libradsec_la_LDFLAGS = -version-info 1:0:0 -export-symbols radsec.sym
libradsec_la_CFLAGS = $(AM_CFLAGS) -I. -I./include -Werror # -DDEBUG -DDEBUG_LEVENT 

EXTRA_DIST = libradsec.spec radsec.sym radsecproxy-includes
libradsec_la_LIBADD = radius/libradsec-radius.la
