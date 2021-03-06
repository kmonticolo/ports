# $OpenBSD: Makefile,v 1.12 2017/11/17 15:20:00 jca Exp $

COMMENT=		manage large numbers of patches

DISTNAME=		quilt-0.65
REVISION=		0
CATEGORIES=		devel

HOMEPAGE=		http://savannah.nongnu.org/projects/quilt/
MAINTAINER=		Kent R. Spillner <kspillner@openbsd.org>

# GPLv3+
PERMIT_PACKAGE_CDROM=	Yes

MASTER_SITES=		${MASTER_SITE_SAVANNAH:=quilt/}

USE_GMAKE=		Yes

RUN_DEPENDS=		devel/gpatch \
			lang/gawk \
			misc/findutils \
			misc/gnugetopt \
			shells/bash \
			sysutils/coreutils \
			sysutils/ggrep \
			textproc/diffstat \
			textproc/gdiff \
			textproc/gsed

BUILD_DEPENDS=		${RUN_DEPENDS} \
			devel/gettext-tools

CONFIGURE_STYLE=	gnu
CONFIGURE_ARGS=		--with-date=${LOCALBASE}/bin/gdate \
			--with-diff=${LOCALBASE}/bin/gdiff \
			--with-find=${LOCALBASE}/bin/gfind \
			--with-getopt=${LOCALBASE}/bin/gnugetopt \
			--with-grep=${LOCALBASE}/bin/ggrep \
			--with-md5sum=${LOCALBASE}/bin/gmd5sum \
			--with-patch=${LOCALBASE}/bin/gpatch \
			--with-sed=${LOCALBASE}/bin/gsed \
			--without-patch-wrapper \
			--without-rpmbuild


FAKE_FLAGS=		BUILD_ROOT=${WRKINST} \
			etcdir=${PREFIX}/share/examples/quilt

post-configure:
	${SUBST_CMD} ${WRKSRC}/test/delete.test

.include <bsd.port.mk>
