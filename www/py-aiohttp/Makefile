# $OpenBSD: Makefile,v 1.4 2017/01/03 19:28:48 landry Exp $

COMMENT =		http client/server for asyncio

MODPY_EGG_VERSION =	0.22.5
DISTNAME =		aiohttp-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		www
REVISION =		0

# Apache2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += ${MODPY_WANTLIB} pthread

MODULES =		lang/python

MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes

MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}

# py-multidict is python3 only
RUN_DEPENDS =		textproc/py-chardet${MODPY_FLAVOR} \
			www/py-multidict
TEST_DEPENDS =		${RUN_DEPENDS} \
			devel/py-test${MODPY_FLAVOR} \
			www/py-gunicorn${MODPY_FLAVOR}

.include <bsd.port.mk>
