# $OpenBSD$

COMMENT=		HTTPish API around the ruby-openid library

DISTNAME=		rack-openid-1.3.1
CATEGORIES=		security www

HOMEPAGE=		https://github.com/josh/rack-openid

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/ruby

BUILD_DEPENDS =		${RUN_DEPENDS}
RUN_DEPENDS =		security/ruby-openid,${MODRUBY_FLAVOR}>=2.1.8 \
			www/ruby-rack,${MODRUBY_FLAVOR}>=1.1.0

CONFIGURE_STYLE=	ruby gem

.include <bsd.port.mk>
