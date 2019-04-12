# $OpenBSD$

COMMENT =		federated status updater

DISTNAME =		honk-0.1.2

CATEGORIES =		www

HOMEPAGE =		https://humungus.tedunangst.com/r/honk

MAINTAINER =		OpenBSD Ports <ports@openbsd.org>

# ISC
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		${HOMEPAGE}/d/
EXTRACT_SUFX =		.tgz

MODULES =		lang/go
ALL_TARGET =		humungus.tedunangst.com/r/honk

SUBST_VARS +=		VARBASE

HONKDIR =		${DESTDIR}${VARBASE}/www/honk
DOCDIR ?=		${PREFIX}/share/doc/honk

post-install:
	${INSTALL_DATA_DIR} ${HONKDIR}/views
	${INSTALL_DATA} ${MODGO_WORKSPACE}/src/${ALL_TARGET}/views/* \
		${HONKDIR}/views/
	${INSTALL_DATA} ${MODGO_WORKSPACE}/src/${ALL_TARGET}/schema.sql \
		${HONKDIR}/
	${INSTALL_DATA_DIR} ${DOCDIR}
	${INSTALL_DATA} ${MODGO_WORKSPACE}/src/${ALL_TARGET}/README \
		${DOCDIR}/

.include <bsd.port.mk>
