SUBDIRS = po src pixmaps scripts

EXTRA_DIST = autogen.sh \
	     firestarter.spec \
	     firestarter.spec.in \
	     firestarter.console \
	     firestarter.pam \
	     CREDITS \
	     fedora.init \
	     intltool-extract.in \
	     intltool-merge.in \
	     intltool-update.in \
	     $(schema_in_files) \
	     $(Applications_in_files) \
             $(Applications_DATA)

schema_in_files = firestarter.schemas.in
schemadir = @GCONF_SCHEMA_FILE_DIR@
schema_DATA = $(schema_in_files:.schemas.in=.schemas)
@INTLTOOL_SCHEMAS_RULE@

install-data-local:
	-GCONF_CONFIG_SOURCE=$(GCONF_SCHEMA_CONFIG_SOURCE) $(GCONFTOOL) --makefile-install-rule $(srcdir)/$(schema_DATA)

Applicationsdir = $(datadir)/gnome/apps/Internet
Applications_in_files= firestarter.desktop.in
Applications_DATA = $(Applications_in_files:.desktop.in=.desktop)

@INTLTOOL_DESKTOP_RULE@
