# $OpenBSD: Makefile,v 1.5 2018/11/08 19:02:40 anton Exp $

COMMENT =	yank terminal output to clipboard

V =		1.1.0
DISTNAME =	yank-${V}
CATEGORIES =	sysutils

HOMEPAGE =	https://github.com/mptre/yank
MAINTAINER =	Anton Lindqvist <anton@openbsd.org>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	https://github.com/mptre/yank/releases/download/v${V}/

# uses pledge()
WANTLIB +=	c

RUN_DEPENDS =	x11/xsel

FAKE_FLAGS =	MANPREFIX=${PREFIX}/man

NO_TEST =	Yes

.include <bsd.port.mk>
