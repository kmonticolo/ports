# $OpenBSD: Makefile,v 1.22 2018/05/25 13:01:41 espie Exp $

COMMENT=		wm-dockapp; calendar/clock

DISTNAME=		wmCalClock-1.25
PKGNAME=		${DISTNAME:L}
REVISION=		1
CATEGORIES=		x11 x11/windowmaker

HOMEPAGE=		http://nis-www.lanl.gov/~mgh/WindowMaker/DockApps.shtml

# GPL
PERMIT_PACKAGE_CDROM=	Yes
WANTLIB=		X11 Xext Xpm c

MASTER_SITES=		http://nis-www.lanl.gov/~mgh/WindowMaker/

NO_TEST=		Yes

WRKSRC=			${WRKDIST}/Src

.include <bsd.port.mk>
