# $OpenBSD: Makefile,v 1.21 2013/10/03 16:37:17 dcoppa Exp $

BROKEN-sparc64 =	ICE in scipy/optimize/minpack/qrsolv.f:189
BROKEN-hppa =		ICE in scipy/special/specfun/specfun.f:5151
BROKEN-alpha =		ICE in scipy/optimize/minpack/lmstr.f:462

COMMENT=		maths, science and engineering modules for Python

MODPY_EGG_VERSION=	0.13.1
DISTNAME=		scipy-${MODPY_EGG_VERSION}
PKGNAME=		py-${DISTNAME}
CATEGORIES=		math devel

MAINTAINER=		Eric Faurot <eric@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += amd blas stdc++ lapack m umfpack util pthread
WANTLIB += ${MODPY_WANTLIB} ${MODFORTRAN_WANTLIB}

MASTER_SITES=		${MASTER_SITE_SOURCEFORGE:=scipy/}
HOMEPAGE=		http://www.scipy.org/

MODULES=		lang/python fortran
MODFORTRAN_COMPILER =	g77
MODPY_SETUPTOOLS=       Yes
MODPY_SETUP=            setupegg.py

BUILD_DEPENDS=		${RUN_DEPENDS} \
			${MODFORTRAN_BUILD_DEPENDS}
LIB_DEPENDS=		math/umfpack \
			math/arpack \
			math/amd \
			${MODFORTRAN_LIB_DEPENDS}
RUN_DEPENDS=		math/py-numpy>=1.8.0 \
			devel/swig

TEST_DEPENDS=	devel/py-nose

MAKE_ENV+=		CPPFLAGS="-I${LOCALBASE}/include/amd -I${LOCALBASE}/include"
MAKE_ENV+=		LDFLAGS="-shared -L${LOCALBASE}/lib -pthread -lutil"
VMEM_WARNING=		Yes

do-test: fake
	${MAKE_ENV} PYTHONPATH=${WRKINST}${MODPY_SITEPKG} ${MODPY_BIN} -c \
		'import scipy ; scipy.test("full")'

.include <bsd.port.mk>
