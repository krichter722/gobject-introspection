AM_CFLAGS = $(GOBJECT_CFLAGS)
AM_LDFLAGS = -module -avoid-version
LIBS = $(GOBJECT_LIBS)

EXTRA_PROGRAMS = gitestrepo gitestthrows gitypelibtest
CLEANFILES = $(EXTRA_PROGRAMS)

gitestrepo_SOURCES = gitestrepo.c
gitestrepo_CPPFLAGS = $(GIREPO_CFLAGS) -I$(top_srcdir)/girepository
gitestrepo_LDADD = $(top_builddir)/libgirepository-1.0.la $(GIREPO_LIBS)

gitestthrows_SOURCES = gitestthrows.c
gitestthrows_CPPFLAGS = $(GIREPO_CFLAGS) -I$(top_srcdir)/girepository
gitestthrows_LDADD = $(top_builddir)/libgirepository-1.0.la $(GIREPO_LIBS)

gitypelibtest_SOURCES = gitypelibtest.c
gitypelibtest_CPPFLAGS = $(GIREPO_CFLAGS) -I$(top_srcdir)/girepository
gitypelibtest_LDADD = $(top_builddir)/libgirepository-1.0.la $(GIREPO_LIBS)

TESTS = gitestrepo gitestthrows gitypelibtest
TESTS_ENVIRONMENT=env GI_TYPELIB_PATH="$(top_builddir):$(top_builddir)/gir:$(top_builddir)/tests:$(top_builddir)/tests/scanner" \
   XDG_DATA_DIRS="$(top_srcdir)/gir:$(XDG_DATA_DIRS)" \
   PATH="$(top_builddir)/tests/scanner/.libs:$(PATH)" \
   LD_LIBRARY_PATH="$(top_builddir)/tests/scanner/.libs:$(LD_LIBRARY_PATH)" \
   $(DEBUG)
