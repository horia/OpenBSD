# $OpenBSD$

COMMENT =		federated status updater

VERSION =		0.1.2
DISTNAME =		honk

CATEGORIES =		www

HOMEPAGE =		https://humungus.tedunangst.com/r/honk

MAINTAINER =		OpenBSD Ports <ports@openbsd.org>

# ISC
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		https://humungus.tedunangst.com/r/honk/d/
DISTFILES =		${DISTNAME}-${VERSION}${EXTRACT_SUFX}
EXTRACT_SUFX =		.tgz
PKGNAME =		${DISTNAME}-${VERSION}

MODULES =		lang/go

MODGO_SUBDIR =		${WRKDIST}-${VERSION}
MODGO_FLAGS +=		-tags "tedunangst.com"

ALL_TARGET =		${DISTNAME}
WRKSRC =		${MODGO_WORKSPACE}/src/${ALL_TARGET}

SUBST_VARS +=		DISTNAME VARBASE

HONKDIR =		${DESTDIR}${VARBASE}/www/${DISTNAME}
DOCDIR ?=		${PREFIX}/share/doc/${DISTNAME}

post-install:
	${INSTALL_DATA_DIR} ${HONKDIR}/views
	${INSTALL_DATA} ${MODGO_WORKSPACE}/src/${DISTNAME}/views/* \
		${HONKDIR}/views/
	${INSTALL_DATA} ${MODGO_WORKSPACE}/src/${DISTNAME}/schema.sql \
		${HONKDIR}/
	${INSTALL_DATA_DIR} ${DOCDIR}
	${INSTALL_DATA} ${MODGO_WORKSPACE}/src/${DISTNAME}/README \
		${DOCDIR}/

.include <bsd.port.mk>
