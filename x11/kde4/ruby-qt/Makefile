# $OpenBSD: Makefile,v 1.28 2018/10/26 16:13:50 jeremy Exp $

BROKEN-hppa =	relocation error
CATEGORIES =	devel x11/kde4
COMMENT =	Ruby bindings for Qt4
DISTNAME =	qtruby-${MODKDE4_VERSION}
PKGNAME =	qt4-${MODKDE4_VERSION}
REVISION =	7

HOMEPAGE =	http://techbase.kde.org/Development/Languages/Ruby

SHARED_LIBS =	qtruby4shared		51.0 # 2.0

WANTLIB =  ${MODRUBY_WANTLIB}
WANTLIB += ${COMPILER_LIBCXX}
WANTLIB += lib/qt4/QtDBus lib/qt4/QtDeclarative lib/qt4/QtGui
WANTLIB += lib/qt4/QtNetwork lib/qt4/QtScript lib/qt4/QtWebKit
WANTLIB += lib/qt4/QtXml
WANTLIB += ${KDE4LIB}/smokebase ${KDE4LIB}/smokephonon ${KDE4LIB}/smokeqsci
WANTLIB += ${KDE4LIB}/smokeqtcore ${KDE4LIB}/smokeqtdbus
WANTLIB += ${KDE4LIB}/smokeqtdeclarative ${KDE4LIB}/smokeqtgui
WANTLIB += ${KDE4LIB}/smokeqtnetwork ${KDE4LIB}/smokeqtopengl
WANTLIB += ${KDE4LIB}/smokeqtscript ${KDE4LIB}/smokeqtsql
WANTLIB += ${KDE4LIB}/smokeqtsvg ${KDE4LIB}/smokeqttest
WANTLIB += ${KDE4LIB}/smokeqtuitools ${KDE4LIB}/smokeqtwebkit
WANTLIB += ${KDE4LIB}/smokeqtxml ${KDE4LIB}/smokeqwt
WANTLIB += qscintilla2_qt4

MODULES =	multimedia/phonon lang/ruby
MODKDE4_USE =

# Remember update @conflict markers in PLIST when changing FLAVORS.
FLAVORS =		ruby24 ruby25
MODRUBY_HANDLE_FLAVORS=	Yes
MODRUBY_ADJ_FILES =	*.rb rbqtapi
SUBST_VARS =		MODRUBY_FLAVOR

CONFIGURE_ARGS =	-DRUBY_EXECUTABLE=${RUBY}

LIB_DEPENDS =	${MODKDE4_DEP_DIR}/smokeqt

NO_TEST =	Yes

.include <bsd.port.mk>
