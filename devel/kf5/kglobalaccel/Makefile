# $OpenBSD: Makefile,v 1.10 2018/10/22 20:30:42 rsadowski Exp $

COMMENT =	global desktop keyboard shortcuts for KDE
DISTNAME =	kglobalaccel-${VERSION}

SHARED_LIBS =	KF5GlobalAccel		4.2
SHARED_LIBS +=	KF5GlobalAccelPrivate	4.2

WANTLIB += ${COMPILER_LIBCXX} KF5ConfigCore KF5CoreAddons KF5Crash
WANTLIB += KF5DBusAddons KF5WindowSystem Qt5Core Qt5DBus Qt5Gui
WANTLIB += Qt5Widgets Qt5X11Extras c m xcb xcb-keysyms

LIB_DEPENDS =	devel/kf5/kconfig \
		devel/kf5/kcoreaddons \
		devel/kf5/kcrash \
		devel/kf5/kdbusaddons \
		devel/kf5/kwindowsystem \
		x11/qt5/qtx11extras

TEST_IS_INTERACTIVE =	X11

.include <bsd.port.mk>
