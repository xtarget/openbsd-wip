# $OpenBSD$

COMMENT =		testing and/or dropping DHCP server

DISTNAME =		dhcdrop-0.5

CATEGORIES =		net

HOMEPAGE =		http://www.netpatch.ru/dhcdrop.html

MAINTAINER =		Kirill Bychkov <kirby@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		c pcap

MASTER_SITES =		http://www.netpatch.ru/projects/dhcdrop/
EXTRACT_SUFX =		.tar.bz2

CONFIGURE_STYLE =	gnu

post-extract:
	perl -pi -e 's/\r$$//' ${WRKSRC}/man/dhcdrop.8
	perl -pi -e 's/\s+$$/\n/' ${WRKSRC}/man/dhcdrop.8

.include <bsd.port.mk>
