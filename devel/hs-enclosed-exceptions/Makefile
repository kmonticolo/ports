# $OpenBSD: Makefile,v 1.4 2018/01/22 21:40:32 kili Exp $

COMMENT =		catch exceptions from within an enclosed computation

DISTNAME =		enclosed-exceptions-1.0.1.1
REVISION =		2
CATEGORIES =		devel

# BSD3
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/ghc
MODGHC_BUILD =		cabal hackage haddock register

MODGHC_PACKAGE_KEY =	7zCD8kFoQDfIxSqvg8gOHx

BUILD_DEPENDS =		${RUN_DEPENDS}

RUN_DEPENDS =		devel/hs-async>=2.0 \
			devel/hs-lifted-base>=0.2 \
			devel/hs-monad-control \
			devel/hs-transformers-base

.include <bsd.port.mk>
