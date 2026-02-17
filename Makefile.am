ACLOCAL_AMFLAGS = -I m4
pkglibdir = $(ROFI_PLUGINS_DIR)

pkglib_LTLIBRARIES = myplugin.la

myplugin_la_SOURCES=\
		 src/myplugin.c

myplugin_la_CFLAGS = @glib_CFLAGS@ @rofi_CFLAGS@
myplugin_la_LIBADD = @glib_LIBS@ @rofi_LIBS@
myplugin_la_LDFLAGS= -module -avoid-version

# Remove libtool archives + strip the shared library
install-exec-hook:
	rm -f $(DESTDIR)$(pkglibdir)/$(pkglib_LTLIBRARIES)
	$(STRIP) $(DESTDIR)$(pkglibdir)/myplugin.so
