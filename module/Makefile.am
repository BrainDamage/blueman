BUILT_SOURCES = _blueman.c

bluemanlibdir = $(pyexecdir)
bluemanlib_LTLIBRARIES = _blueman.la
_blueman_la_CFLAGS = $(BLUEZ_CFLAGS) $(PYGOBJECT_CFLAGS) $(PYTHON_CFLAGS) \
                     -DSN_API_NOT_YET_FROZEN
_blueman_la_LDFLAGS = -module -avoid-version -fPIC
_blueman_la_LIBADD = $(BLUEZ_LIBS) $(PYGOBJECT_LIBS) $(PYTHON_LIBS)
_blueman_la_SOURCES = \
	_blueman.c			\
	libblueman.c	\
	libblueman.h	\
	modem-prober.h \
	modem-prober.c

_blueman.c: _blueman.pyx
	$(PYREXC) -o $@ $<
	
EXTRA_DIST = _blueman.pyx
CLEANFILES = _blueman.c
