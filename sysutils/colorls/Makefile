# $OpenBSD: Makefile,v 1.36 2018/04/04 19:02:00 naddy Exp $

COMMENT=	ls(1) that can use color to display file attributes

VERSION=	6.3
DISTNAME=	ls-${VERSION}
PKGNAME=	colorls-${VERSION}
CATEGORIES=	sysutils

MAINTAINER=	Christian Weisgerber <naddy@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=	http://shell.uugrn.org/~naddy/

WANTLIB=	c curses util

WRKDIST=	${WRKDIR}/ls
NO_TEST=	Yes

# copy file and substitute a string near a CVS keyword
pre-patch:
	sed 's/^\.Dt LS/.Dt COLORLS/' ${WRKSRC}/ls.1 >${WRKSRC}/colorls.1

.include <bsd.port.mk>
