# $OpenBSD: Makefile,v 1.27 2018/06/27 21:03:55 espie Exp $

COMMENT =	beginner's drill tool to learn Japanese kana characters

DISTNAME =	kanatest-0.4.6
REVISION=	10

CATEGORIES =	japanese

# GPL
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama
WANTLIB += Xrandr Xrender atk-1.0 c cairo fontconfig freetype
WANTLIB += gdk-x11-2.0 gdk_pixbuf-2.0 gio-2.0 glib-2.0 gobject-2.0
WANTLIB += gtk-x11-2.0 iconv intl lzma m pango-1.0 pangocairo-1.0
WANTLIB += pangoft2-1.0 xml2 z

MASTER_SITES =	${HOMEPAGE}

BUILD_DEPENDS =	devel/gettext-tools
RUN_DEPENDS =	devel/desktop-file-utils
LIB_DEPENDS =	devel/gettext \
		x11/gtk+2 \
		textproc/libxml

CONFIGURE_STYLE = gnu
CONFIGURE_ENV =	CPPFLAGS="-I${LOCALBASE}/include" \
                LDFLAGS="-L${LOCALBASE}/lib"

NO_TEST =	Yes

.include <bsd.port.mk>
