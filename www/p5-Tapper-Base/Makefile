# $OpenBSD $

COMMENT=	common functions for all Tapper classes	

MODULES=	cpan
DISTNAME=	Tapper-Base-4.1.4
PKGNAME=	p5-${DISTNAME:S/-perl-/-/}
CATEGORIES=	www

MAINTAINER =    Sergey Bronnikov <estetus@gmail.com>

# BSD
PERMIT_PACKAGE_CDROM=	Yes

RUN_DEPENDS=    devel/p5-LockFile-Simple \
		devel/p5-Module-Find

BUILD_DEPENDS=  ${RUN_DEPENDS}

.include <bsd.port.mk>
