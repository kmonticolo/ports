# $OpenBSD: Makefile,v 1.10 2018/07/29 11:27:44 ajacoutot Exp $

COMMENT=		companion library to GObject and Gtk+

GNOME_PROJECT=		libdazzle
GNOME_VERSION=		3.28.5

SHARED_LIBS +=  dazzle-1.0                1.0 # 0

CATEGORIES=		devel

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c cairo gdk-3 gdk_pixbuf-2.0 gio-2.0 glib-2.0 gobject-2.0
WANTLIB += gtk-3 intl m pango-1.0

# -std=gnu11
COMPILER=		base-clang ports-gcc ports-clang

MODULES=		devel/meson \
			x11/gnome

MODGNOME_TOOLS=		gobject-introspection vala

MODGNOME_LDFLAGS=	-L${X11BASE}/lib

LIB_DEPENDS=		x11/gtk+3

.include <bsd.port.mk>
