# $OpenBSD: Makefile,v 1.1.1.1 2018/09/14 15:17:26 rsadowski Exp $

COMMENT =	daemon used to register global keyboard shortcuts

VERSION =	0.13.0

NAME =		lxqt-globalkeys
DISTNAME =	${NAME}-${VERSION}

SHARED_LIBS +=  lxqt-globalkeys-ui        0.0 # 0.13
SHARED_LIBS +=  lxqt-globalkeys           0.0 # 0.13

WANTLIB += ${COMPILER_LIBCXX} ICE KF5WindowSystem Qt5Core Qt5DBus
WANTLIB += Qt5Gui Qt5Svg Qt5Widgets Qt5X11Extras Qt5Xdg Qt5XdgIconLoader
WANTLIB += Qt5Xml SM X11 Xext c lxqt m

LIB_DEPENDS +=		x11/lxqt/liblxqt

BUILD_DEPENDS +=	x11/lxqt/build-tools

RUN_DEPENDS +=		devel/desktop-file-utils

CONFIGURE_ARGS +=	-DPULL_TRANSLATIONS:BOOL=OFF

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/${NAME}
	mv ${WRKINST}${SYSCONFDIR}/xdg ${PREFIX}/share/examples/${NAME}/

.include <bsd.port.mk>
