# $OpenBSD: Makefile,v 1.2 2018/11/11 21:25:27 bentley Exp $

COMMENT =	HTML5 validator

V =		18.11.5
DISTNAME =	vnu.jar_$V
PKGNAME =	vnu-$V

CATEGORIES =	www

HOMEPAGE =	https://validator.github.io/validator/

MAINTAINER =	Anthony J. Bentley <anthony@anjbe.name>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		https://github.com/validator/validator/releases/download/$V/

EXTRACT_SUFX =		.zip

MODULES =		java
MODJAVA_VER =		1.8+
MODJAVA_JRERUN =	Yes
RUN_DEPENDS =		java/javaPathHelper

NO_BUILD =		Yes
NO_TEST =		Yes

WRKDIST =		${WRKDIR}/dist

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/vnu
	${INSTALL_DATA} ${WRKSRC}/vnu.jar ${PREFIX}/share/vnu
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/vnu
	${INSTALL_DATA} ${WRKSRC}/README.md ${PREFIX}/share/doc/vnu
	${SUBST_CMD} -m 555 -c ${FILESDIR}/vnu ${WRKSRC}/vnu
	${INSTALL_SCRIPT} ${WRKSRC}/vnu ${PREFIX}/bin

.include <bsd.port.mk>
