# $OpenBSD: Makefile,v 1.19 2018/11/20 16:46:36 naddy Exp $

COMMENT=	SSL port scanner

V=		1.11.11
GH_ACCOUNT=	rbsec
GH_PROJECT=	sslscan
GH_TAGNAME=	$V-rbsec
DISTNAME=	sslscan-$V
REVISION=	2

CATEGORIES=	security net

HOMEPAGE=	https://github.com/rbsec/sslscan

MAINTAINER=	Stuart Henderson <sthen@openbsd.org>

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

FLAVORS=	openssl
FLAVOR?=

WANTLIB += c

USE_GMAKE=	Yes
NO_TEST=	Yes

MAKE_FLAGS=	BINDIR=${TRUEPREFIX}/bin \
		MANDIR=${TRUEPREFIX}/man \
		GIT_VERSION="$V" \
		CC="${CC}"

SUBST_VARS=	SUFFIX

.if ${FLAVOR:Mopenssl}
BUILD_DEPENDS=	security/openssl/1.0.2:patch
SUFFIX=		-openssl
FULLPKGNAME=	sslscan-openssl-$V
ALL_TARGET=	static
#openssl/libcrypto.a sslscan
#MAKE_FLAGS+=	STATIC_BUILD=TRUE
CFLAGS+=	-nostdinc -I${WRKSRC}/openssl/include -I/usr/include
WANTLIB +=	z

post-extract:
	ln -s ${WRKDIR}/security/openssl/1.0.2/openssl-* ${WRKSRC}/openssl
	-mkdir -p ${WRKSRC}/openssl/.git
	rm -f ${WRKSRC}/openssl/Makefile
.else
WANTLIB +=	crypto ssl
.endif

post-install:
	mv ${PREFIX}/bin/sslscan ${PREFIX}/bin/sslscan${SUFFIX}
	mv ${PREFIX}/man/man1/sslscan.1 ${PREFIX}/man/man1/sslscan${SUFFIX}.1

.include <bsd.port.mk>
