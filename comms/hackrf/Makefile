# $OpenBSD: Makefile,v 1.1.1.1 2018/11/20 12:46:09 bentley Exp $

COMMENT =	host software for the HackRF One SDR

V =		2018.01.1
DISTNAME =	hackrf-$V

SHARED_LIBS +=  hackrf                    0.0 # 0.5

CATEGORIES =	comms

HOMEPAGE =	https://greatscottgadgets.com/hackrf/

MAINTAINER =	Anthony J. Bentley <anthony@anjbe.name>

# GPLv2+ (tools), 3-clause BSD (library)
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c fftw3f m pthread usb-1.0

MASTER_SITES =		https://github.com/mossmann/hackrf/releases/download/v$V/

EXTRACT_SUFX =		.tar.xz

MODULES =		devel/cmake
LIB_DEPENDS =		devel/libusb1 \
			math/fftw3,float

CONFIGURE_ARGS =	-DCMAKE_C_FLAGS="${CFLAGS} -I${LOCALBASE}/include"

NO_TEST =		Yes

WRKSRC =		${WRKDIST}/host

.include <bsd.port.mk>
