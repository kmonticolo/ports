# $OpenBSD: Makefile,v 1.55 2018/10/27 12:40:13 landry Exp $

COMMENT=	Xfce4 clipboard history panel plugin

XFCE_VERSION=	1.4.3
XFCE_PLUGIN=	clipman

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

MODULES=	x11/xfce4
MODXFCE_DESKTOP_FILE=	Yes
MODXFCE_ICON_CACHE=	Yes
MODXFCE_WANTLIB =	xfce4panel-2.0

LIB_DEPENDS+=	x11/xfce4/xfconf \
		x11/xfce4/libxfce4ui \
		graphics/libqrencode

FAKE_FLAGS =	autostartdir=${PREFIX}/share/examples/xfce4-clipman \
		actionsdir=${PREFIX}/share/examples/xfce4-clipman

WANTLIB =	ICE SM X11 Xcomposite Xcursor Xdamage Xext \
		Xfixes Xi Xinerama Xrandr Xrender atk-1.0 c cairo dbus-1 \
		dbus-glib-1 expat fontconfig freetype fribidi \
		gdk_pixbuf-2.0 gio-2.0 glib-2.0 gmodule-2.0 \
		gobject-2.0 m pango-1.0 pangocairo-1.0 \
		pangoft2-1.0 pcre pixman-1 png pthread startup-notification-1 \
		xfce4util z xcb Xtst  xfce4ui-2 \
		X11-xcb ffi xcb-util xfconf-0 qrencode \
		atk-bridge-2.0 atspi cairo-gobject epoxy gdk-3 gtk-3 xfce4panel-2.0 \
		gthread-2.0 xcb-render xcb-shm harfbuzz graphite2 iconv intl

.include <bsd.port.mk>
