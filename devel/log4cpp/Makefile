# $OpenBSD$

CATEGORIES=		devel
COMMENT=		library of C++ classes for flexible logging
VERSION=		1.0
DISTNAME=		log4cpp-${VERSION}
HOMEPAGE=		http://log4cpp.sourceforge.net/

SHARED_LIBS=		log4cpp		0.0

MAINTAINER=		Rafael Sadowski <rafael@sizeofvoid.org>

# LGPL
PERMIT_PACKAGE_CDROM=	No
PERMIT_PACKAGE_FTP=	No
PERMIT_DISTFILES_FTP=	No

MASTER_SITES=		http://www.sizeofvoid.org/pub/OpenBSD/distfiles/

CONFIGURE_ARGS+=	--with-pthreads --disable-html-docs

CONFIGURE_STYLE=	gnu

USE_GMAKE=		Yes

SEPARATE_BUILD=		Yes
CONFIGURE_ARGS=		${CONFIGURE_SHARED}

.include <bsd.port.mk>
