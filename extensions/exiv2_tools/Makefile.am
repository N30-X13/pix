if ENABLE_EXIV2

SUBDIRS = data

extensiondir = $(pkglibdir)/extensions
extension_LTLIBRARIES = libexiv2_tools.la

libexiv2_tools_la_SOURCES = 		\
	exiv2-utils.h			\
	exiv2-utils.cpp			\
	gth-edit-iptc-page.c		\
	gth-edit-iptc-page.h		\
	gth-metadata-provider-exiv2.c	\
	gth-metadata-provider-exiv2.h	\
	main.c

libexiv2_tools_la_CPPFLAGS = $(PIX_CFLAGS) $(EXIV2_CFLAGS) -I$(top_srcdir) -I$(top_builddir)/pix 
libexiv2_tools_la_LDFLAGS = $(EXTENSION_LIBTOOL_FLAGS)
libexiv2_tools_la_LIBADD = $(PIX_LIBS) $(EXIV2_LIBS) ../edit_metadata/libedit_metadata.la
libexiv2_tools_la_DEPENDENCIES = $(top_builddir)/pix/pix$(EXEEXT)

extensioninidir = $(extensiondir)
extensionini_DATA = $(extensionini_in_files:.extension.in.in=.extension)
DISTCLEANFILES = $(extensionini_DATA)

endif

extensionini_in_files = exiv2_tools.extension.in.in

@PIX_EXTENSION_IN_RULE@
@PIX_EXTENSION_RULE@

EXTRA_DIST = $(extensionini_in_files)

-include $(top_srcdir)/git.mk
