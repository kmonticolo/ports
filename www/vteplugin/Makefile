# $OpenBSD: Makefile,v 1.21 2017/11/21 00:13:04 naddy Exp $

COMMENT =	npapi vte-based terminal for web browsers

DISTNAME =	vteplugin-0.1
REVISION =	13
CATEGORIES =	www x11

# WTFPL
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB =  X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama Xrandr
WANTLIB += Xrender atk-1.0 cairo fontconfig freetype gdk-x11-2.0
WANTLIB += gdk_pixbuf-2.0 gio-2.0 glib-2.0 gobject-2.0 gtk-x11-2.0 iconv
WANTLIB += intl m pango-1.0 pangocairo-1.0 pangoft2-1.0 pthread vte z

EXTRACT_SUFX=.tar.bz2

MASTER_SITES =	http://blog.renevier.net/public/
LIB_DEPENDS =	devel/vte

do-build:
	${CC} ${CFLAGS} -fPIC `pkg-config --cflags vte` ${WRKSRC}/npunix.c -c -o ${WRKSRC}/npunix.o
	${CC} ${CFLAGS} -fPIC `pkg-config --cflags vte` ${WRKSRC}/vteplugin.c -c -o ${WRKSRC}/vteplugin.o
	${CC}  -Wl,-Bdynamic -pthread ${WRKSRC}/npunix.o ${WRKSRC}/vteplugin.o -shared \
		-o ${WRKSRC}/vteplugin.so `pkg-config --libs vte gtk+-2.0 gdk-2.0`

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/vteplugin ${PREFIX}/lib/mozilla/plugins/
	${INSTALL_PROGRAM} ${WRKSRC}/vteplugin.so ${PREFIX}/lib/mozilla/plugins/vteplugin.so
	${INSTALL_DATA} ${WRKSRC}/vteplugin.html ${PREFIX}/share/vteplugin/vteplugin.html

.include <bsd.port.mk>
