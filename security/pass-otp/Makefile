# $OpenBSD: Makefile,v 1.3 2018/07/10 12:29:21 gonzalo Exp $

COMMENT =	OTP extension for password-store

V =		1.1.1
DISTNAME =	pass-otp-${V}

CATEGORIES =	security

HOMEPAGE =	https://github.com/tadfisher/pass-otp

MAINTAINER =	Aaron Bieber <abieber@openbsd.org>

# GPLv3+
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =	https://github.com/tadfisher/pass-otp/releases/download/v${V}/

BUILD_DEPENDS =	shells/bash
RUN_DEPENDS =	security/password-store \
		security/oath-toolkit \
		shells/bash \
		graphics/libqrencode

TEST_DEPENDS =	${RUN_DEPENDS} \
		lang/expect

MAKE_FLAGS =	SHELL=${LOCALBASE}/bin/bash
FAKE_FLAGS =	PREFIX=${PREFIX} \
		MANDIR=${PREFIX}/man

USE_GMAKE =	Yes

NO_BUILD =	Yes

.include <bsd.port.mk>
