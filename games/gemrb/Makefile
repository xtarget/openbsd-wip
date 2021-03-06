# $OpenBSD$

SHARED_ONLY = 		Yes

SHARED_LIBS += 		gemrb_core 0.0

COMMENT =		open-source implementation of Bioware's Infinity Engine

DISTNAME =		gemrb-0.8.0.1

CATEGORIES =		games emulators x11

HOMEPAGE =		http://gemrb.sourceforge.net/

MAINTAINER =		Kirill Bychkov <kirby@openbsd.org>

# GPLv2
PERMIT_PACKAGE_CDROM =	Yes

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=gemrb/}

WANTLIB += SDL SDL_mixer c freetype m openal png pthread stdc++
WANTLIB += vorbisfile z ${MODPY_WANTLIB}

MODULES =		converters/libiconv devel/cmake lang/python
LIB_DEPENDS =		devel/sdl-mixer \
			graphics/png \
			audio/openal \
			audio/libvorbis \
			${MODPY_LIB_DEPENDS}
RUN_DEPENDS = 		devel/desktop-file-utils \
			x11/gtk+2,-guic

CONFIGURE_ARGS +=	-DCMAKE_BUILD_TYPE=Release \
			-DSYSCONF_DIR=${SYSCONFDIR}/gemrb/ \
			-DEXAMPLE_CONF_DIR=${PREFIX}/share/examples/gemrb/ \
			-DMAN_DIR=${PREFIX}/man/man6 \
			-DCMAKE_MODULE_LINKER_FLAGS=-lc \
			-DDISABLE_WERROR=1

NO_TEST =		Yes

post-install:
	 cd ${PREFIX}/share/gemrb/GUIScripts/ && find * -name \*.py \
		-exec ${MODPY_BIN} ${MODPY_LIBDIR}/compileall.py ${PREFIX}/share/gemrb/GUIScripts/{} \;

.include <bsd.port.mk>
