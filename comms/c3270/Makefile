# $OpenBSD: Makefile,v 1.7 2017/11/13 22:05:33 jeremy Exp $

COMMENT=	curses-based 3270 terminal editor

DISTNAME=	suite3270-3.5ga11-src
PKGNAME=	c3270-3.5.11
EXTRACT_SUFX=	.tgz
CATEGORIES=	comms

HOMEPAGE=	http://x3270.bgp.nu/

MAINTAINER=	Jeremy Evans <jeremy@openbsd.org>

# BSD-like
PERMIT_PACKAGE_CDROM=	Yes
WANTLIB=		c crypto iconv ssl ncursesw readline util

LIB_DEPENDS=		converters/libiconv

MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=x3270/}

WRKDIST=		${WRKDIR}/suite3270-3.5
USE_GMAKE =		Yes
CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

CONFIGURE_ARGS=		--disable-unix \
			--disable-windows \
			--disable-x3270 \
			--enable-c3270 \
			--disable-s3270 \
			--disable-tcl3270 \
			--disable-pr3287 \
			--disable-lib \
			--disable-wc3270 \
			--disable-ws3270 \
			--disable-wpr3287 \
			--disable-windows-lib

post-install:
	rm ${WRKINST}/etc/x3270/ibm_hosts
	rmdir ${WRKINST}/etc/x3270

NO_TEST=		Yes

.include <bsd.port.mk>
