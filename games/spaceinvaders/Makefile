# $OpenBSD: Makefile,v 1.5 2017/06/08 10:25:01 mglocker Exp $

COMMENT =		curses-based version of the Space Invaders game
DISTNAME =		spaceinvaders-1.4
CATEGORIES =		games
HOMEPAGE =		http://www.nazgul.ch/dev_spaceinvaders.html
MAINTAINER =		Marcus Glocker <marcus@nazgul.ch>

# BSD
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB = 		c curses
MASTER_SITES = 		http://www.nazgul.ch/dev/
NO_TEST =		Yes

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/spaceinvaders ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/spaceinvaders.6 ${PREFIX}/man/man6
	${INSTALL_DATA_DIR} ${PREFIX}/share/spaceinvaders
	${INSTALL_DATA} ${WRKSRC}/README ${PREFIX}/share/spaceinvaders
	${INSTALL_DATA} ${WRKSRC}/ChangeLog ${PREFIX}/share/spaceinvaders

.include <bsd.port.mk>
