# $OpenBSD: Makefile,v 1.16 2018/04/28 10:44:26 pvk Exp $

COMMENT =	Python 2 and 3 compatibility library
MODPY_EGG_VERSION =	1.11.0
DISTNAME =	six-${MODPY_EGG_VERSION}
PKGNAME =	py-six-${MODPY_EGG_VERSION}
CATEGORIES =	devel

HOMEPAGE =	http://pythonhosted.org/six/

MAINTAINER =	Alexandr Shadchin <shadchin@openbsd.org>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MODPY_PI =	Yes

MODULES =	lang/python
MODPY_SETUPTOOLS =	Yes

TEST_DEPENDS =	devel/py-py${MODPY_FLAVOR} \
		devel/py-test${MODPY_FLAVOR}

FLAVORS =	python3
FLAVOR ?=

do-test:
	cd ${WRKSRC} && ${MODPY_BIN} -m pytest -v

.include <bsd.port.mk>
