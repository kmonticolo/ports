# $OpenBSD: Makefile,v 1.10 2017/05/02 07:24:25 benoit Exp $

COMMENT =	command-line HTTP client

MODPY_EGG_VERSION =	0.9.8
GH_TAGNAME =	${MODPY_EGG_VERSION}
GH_ACCOUNT =	jkbrzt
GH_PROJECT =	httpie
DISTNAME =	httpie-${MODPY_EGG_VERSION}

CATEGORIES =	www net

HOMEPAGE =	http://httpie.org

# BSD
PERMIT_PACKAGE_CDROM =	Yes

MODULES =	lang/python
MODPY_SETUPTOOLS =	Yes

MODPY_VERSION =		${MODPY_DEFAULT_VERSION_3}

RUN_DEPENDS =	www/py-requests${MODPY_FLAVOR} \
		textproc/py-pygments${MODPY_FLAVOR}
TEST_DEPENDS =	${RUN_DEPENDS} \
		devel/py-test${MODPY_FLAVOR} \
		devel/py-test-httpbin${MODPY_FLAVOR} \
		devel/py-mock${MODPY_FLAVOR}
PORTHOME =	${WRKSRC}

pre-test:
	# check for docutils presence then calls rst2pseudoxml.py
	# our docutils installs rst2pseudoxml
	rm ${WRKSRC}/tests/test_docs.py

.include <bsd.port.mk>
