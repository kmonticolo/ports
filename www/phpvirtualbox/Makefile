# $OpenBSD: Makefile,v 1.25 2018/10/17 14:15:56 sthen Exp $

COMMENT=		web-based VirtualBox front-end
	
V=			5.0-5
DISTNAME=		phpvirtualbox-${V}
PKGNAME=		phpvirtualbox-${V:S/-/./}
REVISION=		2
EXTRACT_SUFX=		.zip

CATEGORIES=		www sysutils

HOMEPAGE=		http://sourceforge.net/projects/phpvirtualbox/

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=phpvirtualbox/}

MODULES=		lang/php
RUN_DEPENDS=		lang/php/${MODPHP_VERSION},-soap

NO_BUILD=		Yes
NO_TEST=		Yes
PKG_ARCH=		*

PREFIX=			${VARBASE}/www
INSTDIR=		${PREFIX}/phpvirtualbox
TINSTDIR=		${TRUEPREFIX}/phpvirtualbox
SUBST_VARS=		INSTDIR TINSTDIR

do-install:
	cp -Rp ${WRKSRC} ${INSTDIR}
	chown -R ${SHAREOWN}:${SHAREGRP} ${INSTDIR}
	rm ${INSTDIR}/{Dockerfile,docker-compose.yml,.{docker,git}ignore}

.include <bsd.port.mk>
