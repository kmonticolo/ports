# $OpenBSD: Makefile,v 1.15 2018/10/24 14:28:09 sthen Exp $

COMMENT =		messagepack (de)serializer

# XXX: 0.5.6 is the last available version of msgpack-python, which has been
# deprecated. Updating to the newer msgpack is currently not an option as some
# of its consumers do not like the renaming.
MODPY_EGG_VERSION =	0.5.6
DISTNAME =		msgpack-python-${MODPY_EGG_VERSION}
PKGNAME =		py-msgpack-${MODPY_EGG_VERSION}
REVISION =		0

CATEGORIES =		net textproc

HOMEPAGE =		https://msgpack.org/

MAINTAINER =		Alexandr Shadchin <shadchin@openbsd.org>

# Apache 2.0
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		${COMPILER_LIBCXX} ${MODPY_WANTLIB} m

COMPILER =		base-clang ports-gcc base-gcc

MODULES =		lang/python
MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes

TEST_DEPENDS =		devel/py-test${MODPY_FLAVOR}

FLAVORS=		python3
FLAVOR?=

do-test:
	@cd ${WRKSRC} && ${MODPY_BIN} -m pytest

.include <bsd.port.mk>
