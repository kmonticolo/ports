# $OpenBSD: Makefile,v 1.24 2016/03/11 19:59:16 naddy Exp $

COMMENT=	strong hash library

DISTNAME=	mhash-0.9.9.9
CATEGORIES=	security
SHARED_LIBS=	mhash	2.1	# .2.1
MODGNU_SHARED_LIBS=mhash ''
LIBmhash_ALIAS=	realmhash
REVISION=	0

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=mhash/}

HOMEPAGE=	http://mhash.sourceforge.net/

MAINTAINER=	Jakob Schlyter <jakob@openbsd.org>

# LGPL
PERMIT_PACKAGE_CDROM=	Yes

CONFIGURE_STYLE= gnu
CONFIGURE_ARGS+= --enable-static

.include <bsd.port.mk>
