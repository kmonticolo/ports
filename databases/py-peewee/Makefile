# $OpenBSD: Makefile,v 1.13 2017/01/03 19:17:24 landry Exp $

PKG_ARCH=		*
COMMENT=		small expressive ORM

MODPY_EGG_VERSION=	2.8.3
DISTNAME=		peewee-${MODPY_EGG_VERSION}
PKGNAME=		py-${DISTNAME}
REVISION=		0

GH_ACCOUNT=		coleifer
GH_PROJECT=		peewee
GH_TAGNAME=		${MODPY_EGG_VERSION}

CATEGORIES=		databases

HOMEPAGE=		http://docs.peewee-orm.com/

# MIT
PERMIT_PACKAGE_CDROM=	Yes

BUILD_DEPENDS=		textproc/py-sphinx${MODPY_FLAVOR}

FLAVORS=		python3
FLAVOR?=

MODULES=		lang/python
MODPY_SETUPTOOLS=	Yes

MAKE_ENV +=	PYTHONPATH=${WRKSRC} SPHINXBUILD=${LOCALBASE}/bin/sphinx-build${MODPY_BIN_SUFFIX}
DOCSRC =	${WRKSRC}/docs
post-build:
	cd ${DOCSRC} && ${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} html

DOCS =		${PREFIX}/share/doc/${MODPY_PY_PREFIX}peewee
EXAMPLES =	${PREFIX}/share/examples/${MODPY_PY_PREFIX}peewee
post-install:
	${INSTALL_DATA_DIR} ${DOCS}
	cd ${DOCSRC}/_build/html && pax -rw * ${DOCS}
	${INSTALL_DATA_DIR} ${EXAMPLES}
	cd ${WRKSRC}/examples && pax -rw * ${EXAMPLES}
	mv ${PREFIX}/bin/pwiz.py ${PREFIX}/bin/pwiz${MODPY_BIN_SUFFIX}

do-test:
	cd ${WRKSRC} && ${MODPY_BIN} tests.py

.include <bsd.port.mk>
