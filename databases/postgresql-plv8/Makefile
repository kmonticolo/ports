# $OpenBSD: Makefile,v 1.17 2018/12/02 13:26:42 ajacoutot Exp $

# v8 only works on these arches currently
ONLY_FOR_ARCHS =	amd64 i386

COMMENT =		PostgreSQL V8 javascript procedural language

VERSION =		1.4.2
REVISION =		7
DISTNAME =		plv8-${VERSION}
PKGNAME =		postgresql-${DISTNAME}

CATEGORIES =		databases

HOMEPAGE =		https://github.com/plv8/plv8

# BSD
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c m ${COMPILER_LIBCXX} pthread v8

MASTER_SITES =		http://api.pgxn.org/dist/plv8/${VERSION}/
EXTRACT_SUFX =		.zip

COMPILER =		base-clang ports-gcc base-gcc

BUILD_DEPENDS =		${RUN_DEPENDS}
LIB_DEPENDS =		lang/libv8
RUN_DEPENDS =		postgresql-server->=10,<11:databases/postgresql,-server

MAKE_FLAGS =		V8DIR=${LOCALBASE}/lib \
			CUSTOM_CC="${CXX}" \
			OPTFLAGS="${CXXFLAGS}"
USE_GMAKE =		Yes

# Need to start the PostgreSQL server first
TEST_IS_INTERACTIVE=	Yes
TEST_DEPENDS =	${FULLPKGNAME}:${BUILD_PKGPATH}

do-test:
	cd ${WRKSRC} && ${SETENV} ${MAKE_ENV} PGUSER=postgres \
		gmake installcheck

.include <bsd.port.mk>
