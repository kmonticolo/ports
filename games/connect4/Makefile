# $OpenBSD: Makefile,v 1.36 2018/07/15 08:36:38 espie Exp $

COMMENT=	curses version of the classic game

DISTNAME=	connect4
PKGNAME=	connect4-3.2
REVISION=	2
CATEGORIES=	games

# License: NONE
PERMIT_PACKAGE_CDROM=	no license
PERMIT_PACKAGE_FTP=	no license
PERMIT_DISTFILES_FTP=	no license
WANTLIB=		c curses termcap

MASTER_SITES= 	${MASTER_SITE_FREEBSD}
EXTRACT_SUFX=	.Z
EXTRACT_CASES=	*.Z) ${GZIP_CMD} -dc ${FULLDISTDIR}/$$archive | \
		${_PERL_FIX_SHAR} | /bin/sh ;;

MAKE_FLAGS=	CFLAGS='${CFLAGS} -DSCOREFILE=\"/var/games/connect4.scores\"'

ALL_TARGET=	c4

WRKDIST=	${WRKDIR}

NO_TEST=	Yes

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/c4 ${PREFIX}/bin/connect4
	@chown root:games ${PREFIX}/bin/connect4
	@chmod 2755 ${PREFIX}/bin/connect4
	${INSTALL_MAN} ${FILESDIR}/connect4.6 ${PREFIX}/man/man6
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/connect4
	${INSTALL_DATA} /dev/null ${PREFIX}/share/examples/connect4/connect4.scores

.include <bsd.port.mk>
